## Get kubeconfig and password
```
# kubeconfig of Spoke cluster
oc -n cnfde10 get secret cnfde10-admin-kubeconfig -o jsonpath='{.data.kubeconfig}' | base64 -d > ~/.kube/kubeconfig.cnfde10

# admin password of Spoke cluster
oc get secret -n cnfde10 cnfde10-admin-password -o jsonpath='{.data.password}' | base64 -d; echo

# Argo CD Password:
oc get secret -n openshift-gitops openshift-gitops-cluster -o jsonpath='{.data.admin\.password}' | base64 -d; echo
```
## ACM /ZTP
```
oc describe -n cnfde10 agentclusterinstall
oc get clusterimagesets
oc adm release info
# get ClusterOperator
oc get co





```
## Add a new openshift release in ACM
### For each new y-stream (e.g. 4.9, 4.10, ...) add a new entry in the AgentServiceConfig CR on the hub.

Example: [data/AgentServiceConfig.yaml](data/AgentServiceConfig.yaml)

### For each new z-stream (e.g.4.10.2, 4.11.0-0.nightly-xxx...) you need a new ClusterImageSet.

Just copy an existing one:

```
oc get clusterimageset openshift-v4.10.6 -o yaml > my_cis.yaml
```

Then edit the my_cis.yaml to look like this:
```
apiVersion: hive.openshift.io/v1
kind: ClusterImageSet
metadata:
  name: openshift-4.11.0-0.nightly-2022-04-08-205307
spec:
  releaseImage: quay.io/openshift-release-dev/ocp-release:4.11.0-0.nightly-2022-04-08-205307
```
Example: [data/ClusterImageSet.yaml](data/ClusterImageSet.yaml)

Then apply it:
```
oc apply -f my_cis.yaml
```

You could also change the name of the cis to be "jacks_cis". Then edit the same cis each time you want to deploy a different version.

## Port forwarding
```
# oc port-forward hw-event-proxy-5c4cf9b7c8-jxlq6 --address localhost 8089:8089 &
oc port-forward hw-event-proxy-5c4cf9b7c8-jxlq6 8089:8089 &
```
explore API at browser:

* http://localhost:8089/api/cloudNotifications/v1/publishers
* http://localhost:8089/api/cloudNotifications/v1/subscriptions
* http://localhost:8089/api/cloudNotifications/v1/health


## Encoding K8s secret
```
echo -n 'super-secret-password' | base64
```
https://www.cloudytuts.com/tutorials/kubernetes/how-to-base64-encode-kubernetes-secrets/

Always remember to set the -n flag for echo when encoding secrets. The flag prevents trailing newline characters from being encoded. Hidden characters in base64 encoded secrets will result in improperly formed strings, which will cause you grief with Kubernetes.

## Worker node failde to deploy
If baremetal worker node does not show up in `oc get nodes`. It might have failed to deploy due to pending csr.

Check if there is any pending csr. Normally `oc get csr` should just show `No resources found`.

```
# oc get csr
NAME        AGE     SIGNERNAME                                    REQUESTOR                                                                   REQUESTEDDURATION   CONDITION
csr-45jvr   55m     kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   <none>              Pending
csr-f2pgv   102m    kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   <none>              Pending
```
### Fix: sign all the pending CSR
https://openshift.tips/certificates/#sign-all-the-pending-csr

```
oc get csr -o name | xargs oc adm certificate approve
```

## Login to openshift registry

https://source.redhat.com/groups/public/kubernetes_native_infrastructure/foundation_wiki/ocp_custom_release_notes

### Login with Podman
```
Go to https://oauth-openshift.apps.ci.l2s4.p1.openshiftapps.com/oauth/token/request
Login with your github credentials
Click to display the credential, and copy the token
podman login -u jzding -p token registry.ci.openshift.org
```

### Login with docker
```
systemctl start docker

# use the API token as Password.
$ docker login registry.ci.openshift.org
Authenticating with existing credentials...
Stored credentials invalid or expired
Username (username): jzding
Password: sha256~KesiuAEXir1_m0HmCzRgcoUTbX5mVWx2mgFS4yCrfNI

```


## 4.10
quay.io/openshift-release-dev/ocp-release-nightly:4.10.0-0.nightly-2021-12-14-083101

## kuttl

export GO111MODULE=off
go get github.com/kudobuilder/kuttl
cd go/src/github.com/kudobuilder/kuttl
make cli-install


## Delete stuck namespace
```
oc get ns cloud-native-events -o json >tmp.json

# edit tmp.json: empty "finalizers" and delete "status"

  "spec": {
    "finalizers": []
  }
}

# in a seperate shell start a local web server: 
# Starting to serve on 127.0.0.1:8001
kubectl proxy

# This will delete the namespace cloud-native-events
curl -k -H "Content-Type: application/json" -X PUT --data-binary @tmp.json http://127.0.0.1:8001/api/v1/namespaces/cloud-native-events/finalize


# or delete stuc resources
kubectl api-resources | grep -i false
kubectl delete apiservice v1beta1.metrics.k8s.io

```

## Run baremetal-operator from local source checkout
https://github.com/openshift-metal3/dev-scripts/blob/master/docs/custom-mao-and-capbm.md#run-baremetal-operator-from-local-source-checkout

```
mkdir -p /home/jackding/repo/metal3-io/dev-scripts/ocp/ostest/auth/
ln -s ~/.kube/config /home/jackding/repo/metal3-io/dev-scripts/ocp/ostest/auth/kubeconfig


oc logs -f $(oc get pods -n openshift-machine-api | grep metal3-development | awk '{print $1}') -n openshift-machine-api -c metal3-ironic-api
```

## Misc
```

[root@cnfdt15-installer ~]# env | grep OS_
OS_CLOUD=metal3
OS_ENDPOINT=http://172.22.0.3:6385


oc -n openshift-machine-api describe bmh cnfdt15-worker-1


$ oc -n openshift-machine-api get bmh cnfdt15-worker-1 -o json | jq .spec.image

$ oc -n openshift-machine-api get bmh cnfdt15-worker-1 -o json | jq .spec.bmc
{
  "address": "idrac-virtualmedia://10.46.61.142/redfish/v1/Systems/System.Embedded.1",
  "credentialsName": "cnfdt15-worker-1-bmc-secret",
  "disableCertificateVerification": true
}
$ oc -n openshift-machine-api get bmh cnfdt15-worker-1 -o json | jq .status.hardware.hostname
"cnfdt15.lab.eng.tlv2.redhat.com"


oc -n openshift-machine-api get BareMetalHost



kubectl get nodes -o json | jq '.items[].metadata.labels'

oc -n openshift-machine-api get pod machine-api-operator-6797c7cd87-wrtl4 -o json | jq '.spec.nodeName'
```
## Lab
```
oc login https://api.cnfdt15.lab.eng.tlv2.redhat.com:6443 -u=kubeadmin -p=vr9FP-rN5ho-jhzCx-WSw6C
oc login https://api.cnfdd2.t5g.lab.eng.bos.redhat.com:6443 -u=kubeadmin -p=SgePn-Am9yA-hJgn3-GHjdg



ssh kni@10.46.55.16  (pass: 123123)
kcli list vm
kcli start vm cnfdt15-installer
```

## Move Docker images to quay.io
```
podman pull registry.ci.openshift.org/ocp/builder:rhel-8-golang-1.17-openshift-4.10
podman push registry.ci.openshift.org/ocp/builder:rhel-8-golang-1.17-openshift-4.10 quay.io/redhat-cne/openshift-origin-release:golang-1.17

podman push registry.ci.openshift.org/ocp/4.10:base quay.io/redhat-cne/openshift-origin-release:base-4.10


```

## Recover Nodes
```
# check node state
oc get mcp

# login to node
ssh core@cnfdt15.lab.eng.tlv2.redhat.com

# Check in the node: After you get in, first two things to check are date - if it is off, you might get this symptom because of TLS failure systemctl status kubelet - if kubelet is erroring on something you will find a clue
[core@cnfdt15 ~]$ date
[core@cnfdt15 ~]$ systemctl status kubelet
```

## YAML syntax check
sudo dnf install yamllint


### Setting objects unmanaged
https://github.com/openshift/enhancements/blob/master/dev-guide/cluster-version-operator/dev/clusterversion.md#setting-objects-unmanaged


oc get clusterversion -o jsonpath='{.status.desired.image}{"\n"}' version

oc -n openshift-monitoring scale deployment grafana --replicas=1
oc -n openshift-monitoring get route grafana
$ oc -n openshift-monitoring get route grafana -o json | jq .spec.host
"grafana-openshift-monitoring.apps.cnfdt15.lab.eng.tlv2.redhat.com"

oc get pod hw-event-proxy-5bdfdddb56-x5bm8 -o json | jq .spec.nodeName

sudo usermod -a -G docker $USER

./_out/deployer validate --json | jq

```
FROM docker.io/openshift/origin-release:golang-1.15 AS go-builder
FROM =docker.io/openshift/origin-base AS bin
```
# Cleanup podman images
podman ps --all
podman rm --force 86c1d99b42a2 349ea14ead62 894a12b579b3 b6f410fe47f4
podman image rm -a

#  Test Dockerfile
podman build -f Dockerfile -t hw-event-proxy:1
podman run -dt 6d41a7ffb4d0
podman exec -it ca81cbbaccea bash

```
registry.ci.openshift.org/ocp/release:4.7.0-0.nightly-2021-07-06-050841
```

[root@cnfdt16-installer ~]# oc get bmh cnfdt16-worker-1 -o yaml | grep redfish

Tests:

# find out token
oc whoami -t

Create a debug pod on the node

oc debug node/cnfdt15.lab.eng.tlv2.redhat.com
sh-4.4# chroot /host




Install openshift-cli (oc) command

https://cloud.redhat.com/openshift/downloads


Access Lab Remotely

1. login to console. 
   For cnfdt15, 
   ssh root@10.46.55.194  (pass: unix1234)
2. Print out password for kubeadmin:
   cat ~/ocp/auth/kubeadmin-password; echo
3. Print out config. Copy the output and save to your PC at ~/.kube/config
   oc config view
4. In your local PC:
   oc login
            Display: You must obtain an API token by visiting https://oauth-openshift.apps.cnfdt15.lab.eng.tlv2.redhat.com/oauth/token/request
      5. click on the url, login with kubeadmin and password from step 2.
           Click "Display Token", and login with instructions:
           c login --token=sha256~1kqT-7T_FueUlASNke1aF2Uvqbp1b1H9-HQsgWtrGnM --server=https://api.cnfdt15.lab.eng.tlv2.redhat.com:6443

Copy kubeconfig from Copy from OCP/auth folder


CodeReady Containers

https://cloud.redhat.com/openshift/create/local

crc delete -f; crc cleanup; crc setup
crc start --log-level debug

Started the OpenShift cluster.

The server is accessible via web console at:
  https://console-openshift-console.apps-crc.testing

Log in as administrator:
  Username: kubeadmin
  Password: e5oqC-d6Rwa-eFBwQ-8yFeX

Log in as user:
  Username: developer
  Password: developer

Use the 'oc' command line interface:
  $ eval $(crc oc-env)
  $ oc login -u developer https://api.crc.testing:6443

oc new-project myproject


---
KCLI Web Interface  http://10.19.16.1/
“Redeploy”

ssh root@10.19.17.187       password: unix1234
~/ocp/.openshift_install.log
tail -f /var/log/cloud-init-output.log


Web Console

## find URL here
oc describe console
or
oc get console -o yaml

username: kubeadmin
password: cat ~/ocp/auth/kubeadmin-password; echo

oc get packagemanifests -n openshift-marketplace



Your API token is

sha256~t09gb5Hqp4ikmQEaJ0vYeO-1lTfR1aJXsn0-mPkBfus

Log in with this token

```
oc login --token=sha256~t09gb5Hqp4ikmQEaJ0vYeO-1lTfR1aJXsn0-mPkBfus --server=https://api.ci.l2s4.p1.openshiftapps.com:6443
```

Use this token directly against the API

```
curl -H "Authorization: Bearer sha256~t09gb5Hqp4ikmQEaJ0vYeO-1lTfR1aJXsn0-mPkBfus" "https://api.ci.l2s4.p1.openshiftapps.com:6443/apis/user.openshift.io/v1/users/~"
```


oc get configmap dns-default -n openshift-dns -o yaml
