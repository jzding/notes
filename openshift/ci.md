## Result of `env`:
```
PWD=/go/src/github.com/redhat-cne/hw-event-proxy-operator

show env:
PROW_JOB_ID=9ead5141-77d2-11ec-aa25-0a580a8320d8
HOSTNAME=e2e-operator-e2e-operator
JOB_TYPE=presubmit
KUBERNETES_PORT=tcp://172.30.0.1:443
KUBERNETES_PORT_443_TCP_PORT=443
TERM=xterm
OPENSHIFT_BUILD_COMMIT=18cc2328d72e34afc97cbb544618600c5c7fb656
OPENSHIFT_CI=true
OPENSHIFT_BUILD_NAME=src
KUBERNETES_SERVICE_PORT=443
PULL_NUMBER=25247
KUBERNETES_SERVICE_HOST=172.30.0.1
KUBEADMIN_PASSWORD_FILE=/var/run/secrets/ci.openshift.io/multi-stage/kubeadmin-password
RELEASE_IMAGE_LATEST=registry.build01.ci.openshift.org/ci-op-ij1nk2y6/release@sha256:d231a9b8944b386eac3d07b1d576ce2941edf726ba2e1f649dc079d6787b9040
JOB_SPEC={"type":"presubmit","job":"rehearse-25247-pull-ci-redhat-cne-hw-event-proxy-operator-main-e2e-operator","buildid":"1483171864313335808","prowjobid":"9ead5141-77d2-11ec-aa25-0a580a8320d8","refs":{"org":"openshift","repo":"release","repo_link":"https://github.com/openshift/release","base_ref":"master","base_sha":"984126f42b0ca0bfd9034b7c54809cf8b3fa9389","base_link":"https://github.com/openshift/release/commit/984126f42b0ca0bfd9034b7c54809cf8b3fa9389","pulls":[{"number":25247,"author":"jzding","sha":"0c13a006699ed194f5a5b5e24e136d8cd6f7c931","link":"https://github.com/openshift/release/pull/25247","commit_link":"https://github.com/openshift/release/pull/25247/commits/0c13a006699ed194f5a5b5e24e136d8cd6f7c931","author_link":"https://github.com/jzding"}]},"extra_refs":[{"org":"redhat-cne","repo":"hw-event-proxy-operator","base_ref":"main","workdir":true}],"decoration_config":{"timeout":"2h0m0s","grace_period":"15s","utility_images":{"clonerefs":"gcr.io/k8s-prow/clonerefs:v20220115-3e20513bd7","initupload":"gcr.io/k8s-prow/initupload:v20220115-3e20513bd7","entrypoint":"gcr.io/k8s-prow/entrypoint:v20220115-3e20513bd7","sidecar":"gcr.io/k8s-prow/sidecar:v20220115-3e20513bd7"},"resources":{"clonerefs":{"limits":{"memory":"3Gi"},"requests":{"cpu":"100m","memory":"500Mi"}},"initupload":{"limits":{"memory":"200Mi"},"requests":{"cpu":"100m","memory":"50Mi"}},"place_entrypoint":{"limits":{"memory":"100Mi"},"requests":{"cpu":"100m","memory":"25Mi"}},"sidecar":{"limits":{"memory":"2Gi"},"requests":{"cpu":"100m","memory":"250Mi"}}},"gcs_configuration":{"bucket":"origin-ci-test","path_strategy":"single","default_org":"openshift","default_repo":"origin","mediaTypes":{"log":"text/plain"}},"gcs_credentials_secret":"gce-sa-credentials-gcs-publisher","skip_cloning":true,"censor_secrets":true}}
OPENSHIFT_BUILD_SOURCE=https://github.com/openshift/release.git
SHARED_DIR=/tmp/secret
CLI_DIR=/cli
ARTIFACT_DIR=/logs/artifacts
NAMESPACE=ci-op-ij1nk2y6
KUBECONFIG=/tmp/kubeconfig-2279749373
BUILD_LOGLEVEL=0
PULL_BASE_SHA=984126f42b0ca0bfd9034b7c54809cf8b3fa9389
CLUSTER_PROFILE_DIR=/var/run/secrets/ci.openshift.io/cluster-profile
IMAGE_HW_EVENT_PROXY_OPERATOR=registry.build01.ci.openshift.org/ci-op-ij1nk2y6/pipeline@sha256:2b7dd6235811d87634f89f0d7e0cd41fcf2c42624c00ec0b4fd23fbcd02633a1
OPENSHIFT_BUILD_NAMESPACE=ci-op-ij1nk2y6
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/local/go/bin:/go/bin:/cli
GOARM=5
PWD=/go/src/github.com/redhat-cne/hw-event-proxy-operator
GOFLAGS=-mod=vendor
VERSION=1.17.5
CLUSTER_TYPE=aws
JOB_NAME=rehearse-25247-pull-ci-redhat-cne-hw-event-proxy-operator-main-e2e-operator
LEASED_RESOURCE=us-west-2
PULL_BASE_REF=master
CLONEREFS_OPTIONS={"src_root":"/go","log":"/dev/null","git_user_name":"ci-robot","git_user_email":"ci-robot@openshift.io","refs":[{"org":"openshift","repo":"release","repo_link":"https://github.com/openshift/release","base_ref":"master","base_sha":"984126f42b0ca0bfd9034b7c54809cf8b3fa9389","base_link":"https://github.com/openshift/release/commit/984126f42b0ca0bfd9034b7c54809cf8b3fa9389","pulls":[{"number":25247,"author":"jzding","sha":"0c13a006699ed194f5a5b5e24e136d8cd6f7c931","link":"https://github.com/openshift/release/pull/25247","commit_link":"https://github.com/openshift/release/pull/25247/commits/0c13a006699ed194f5a5b5e24e136d8cd6f7c931","author_link":"https://github.com/jzding"}]},{"org":"redhat-cne","repo":"hw-event-proxy-operator","base_ref":"main","workdir":true}],"fail":true}
REPO_NAME=release
OPENSHIFT_BUILD_REFERENCE=master
BUILD_ID=1483171864313335808
ENTRYPOINT_OPTIONS={"timeout":7200000000000,"grace_period":15000000000,"artifact_dir":"/logs/artifacts","args":["/bin/bash","-c","#!/bin/bash\nset -eu\necho \"SHARED_DIR=${SHARED_DIR}\"\necho \"KUBECONFIG=${KUBECONFIG}\"\necho \"PWD=${PWD}\"\necho \"show env:\"\nenv\ncp $(echo \"${KUBECONFIG}\") ${PWD}/kubeconfig\nexport IMG=${IMAGE_HW_EVENT_PROXY_OPERATOR}\nmake test-ci\n"],"container_name":"test","process_log":"/logs/process-log.txt","marker_file":"/logs/marker-file.txt","metadata_file":"/logs/artifacts/metadata.json"}
SHLVL=1
HOME=/alabama
GOROOT=/usr/local/go
PULL_REFS=master:984126f42b0ca0bfd9034b7c54809cf8b3fa9389,25247:0c13a006699ed194f5a5b5e24e136d8cd6f7c931
KUBERNETES_PORT_443_TCP_PROTO=tcp
KUBERNETES_SERVICE_PORT_HTTPS=443
CI=true
JOB_NAME_HASH=e85f6
REPO_OWNER=openshift
PULL_PULL_SHA=0c13a006699ed194f5a5b5e24e136d8cd6f7c931
LOGNAME=deadbeef
NSS_SDB_USE_CACHE=no
GOCACHE=/go/.cache
GOPATH=/go
IMAGE_FORMAT=
KUBERNETES_PORT_443_TCP_ADDR=172.30.0.1
KUBERNETES_PORT_443_TCP=tcp://172.30.0.1:443
JOB_NAME_SAFE=e2e-operator
_=/usr/bin/env
```

## Openshift/releas env
```
make ci-operator-config
make jobs
make openshift-image-mirror-mappings


podman run -it centos:7.8.2003

oc get nodes
NAME                           STATUS   ROLES    AGE   VERSION
ip-10-0-129-44.ec2.internal    Ready    master   22m   v1.22.1+6859754
ip-10-0-157-65.ec2.internal    Ready    worker   12m   v1.22.1+6859754
ip-10-0-172-116.ec2.internal   Ready    worker   16m   v1.22.1+6859754
ip-10-0-174-33.ec2.internal    Ready    master   22m   v1.22.1+6859754
ip-10-0-201-139.ec2.internal   Ready    master   23m   v1.22.1+6859754
ip-10-0-223-153.ec2.internal   Ready    worker   11m   v1.22.1+6859754

node/ip-10-0-157-65.ec2.internal labeled

/go/src/github.com/redhat-cne/cloud-event-proxy
NAME                                         STATUS   ROLES    AGE     VERSION
ip-10-0-161-224.us-west-2.compute.internal   Ready    worker   9m1s    v1.22.1+6859754
ip-10-0-168-114.us-west-2.compute.internal   Ready    master   16m     v1.22.1+6859754
ip-10-0-178-112.us-west-2.compute.internal   Ready    master   16m     v1.22.1+6859754
ip-10-0-190-166.us-west-2.compute.internal   Ready    worker   8m9s    v1.22.1+6859754
ip-10-0-222-25.us-west-2.compute.internal    Ready    worker   9m55s   v1.22.1+6859754
ip-10-0-231-197.us-west-2.compute.internal   Ready    master   16m     v1.22.1+6859754

echo ${RELEASE_IMAGE_LATEST}
RELEASE_IMAGE_LATEST:
registry.build03.ci.openshift.org/ci-op-2g1nc05z/release@sha256:febbce0f8dd21764d1980330dd6cf5b524233507f223d22d8b01efe6308cf35c

echo ${IMAGE_CLOUD_EVENT_PROXY}
      - env: IMAGE_CLOUD_EVENT_PROXY
        name: pipeline:cloud-event-proxy     
IMAGE_CLOUD_EVENT_PROXY:
registry.build03.ci.openshift.org/ci-op-2g1nc05z/pipeline@sha256:44e2d6fe1cba15683d24e7dce7a38307ba33a44e10d35ef3893e0f9319ec8a79



https://gcsweb-ci.apps.ci.l2s4.p1.openshiftapps.com/gcs/origin-ci-test/pr-logs/pull/openshift_release/24601/rehearse-24601-pull-ci-redhat-cne-cloud-event-proxy-main-e2e-aws/1470850088036208640/artifacts/e2e-aws/functests/build-log.txt
NAME                                                READY   STATUS              RESTARTS   AGE
cloud-native-consumer-deployment-56d8b685f4-n5nqw   0/2     ContainerCreating   0          3s
"registry.build03.ci.openshift.org/ci-op-2g1nc05z/pipeline@sha256:44e2d6fe1cba15683d24e7dce7a38307ba33a44e10d35ef3893e0f9319ec8a79"


https://gcsweb-ci.apps.ci.l2s4.p1.openshiftapps.com/gcs/origin-ci-test/pr-logs/pull/openshift_release/24601/rehearse-24601-pull-ci-redhat-cne-cloud-event-proxy-main-e2e-aws/1470850088036208640/artifacts/build-logs/cloud-event-proxy.log



# which go
/usr/local/go/bin/go

# go version
go version go1.15.15 linux/amd64

# uname -a
Linux e2e-aws-functests 4.18.0-305.28.1.el8_4.x86_64 #1 SMP Mon Nov 8 07:45:47 EST 2021 x86_64 x86_64 x86_64 GNU/Linux

# cat /etc/redhat-release
CentOS Linux release 7.8.2003 (Core)
LSB Version:	:core-4.1-amd64:core-4.1-noarch
Distributor ID:	CentOS
Description:	CentOS Linux release 7.8.2003 (Core)
Release:	7.8.2003
Codename:	Core

# echo $KUBECONFIG
/tmp/kubeconfig-3486999529

# pwd
/go/src/github.com/redhat-cne/cloud-event-proxy

ls -l
total 144
-rw-rw-r--. 1 root root  5229 Dec  8 18:43 CODE_OF_CONDUCT.md
-rw-rw-r--. 1 root root  1464 Dec  8 18:43 CONTRIBUTING.md
-rw-rw-r--. 1 root root   812 Dec  8 18:43 Dockerfile
-rw-rw-r--. 1 root root   862 Dec  8 18:43 Dockerfile.local
-rw-rw-r--. 1 root root 11357 Dec  8 18:43 LICENSE
-rw-rw-r--. 1 root root  3049 Dec  8 18:43 Makefile
-rw-rw-r--. 1 root root   282 Dec  8 18:43 OWNERS
-rw-rw-r--. 1 root root   217 Dec  8 18:43 OWNERS_ALIASES
-rw-rw-r--. 1 root root  8940 Dec  8 18:43 README.md
drwxrwxr-x. 2 root root    41 Dec  8 18:43 cmd
drwxrwxr-x. 2 root root    46 Dec  8 18:43 docs
drwxrwxr-x. 5 root root   115 Dec  8 18:43 examples
-rw-rw-r--. 1 root root  3506 Dec  8 18:43 go.mod
-rw-rw-r--. 1 root root 82471 Dec  8 18:43 go.sum
drwxrwxr-x. 2 root root   152 Dec  8 18:43 hack
drwxrwxr-x. 6 root root    73 Dec  8 18:43 pkg
drwxrwxr-x. 5 root root    50 Dec  8 18:43 plugins
drwxrwxr-x. 4 root root    30 Dec  8 18:43 test
drwxrwxr-x. 9 root root   154 Dec  8 18:43 vendor

ls -l ~/.kube
ls: cannot access /alabama/.kube: No such file or directory

oc projects
You have access to the following projects and can switch between them with ' project <projectname>':
default
kube-node-lease
kube-public
kube-system
openshift
openshift-apiserver
openshift-apiserver-operator
openshift-authentication
openshift-authentication-operator
openshift-cloud-controller-manager
openshift-cloud-controller-manager-operator
openshift-cloud-credential-operator
openshift-cluster-api
openshift-cluster-csi-drivers
openshift-cluster-machine-approver
openshift-cluster-node-tuning-operator
openshift-cluster-samples-operator
openshift-cluster-storage-operator
openshift-cluster-version
openshift-config
openshift-config-managed
openshift-config-operator
openshift-console
openshift-console-operator
openshift-console-user-settings
openshift-controller-manager
openshift-controller-manager-operator
openshift-dns
openshift-dns-operator
openshift-etcd
openshift-etcd-operator
openshift-host-network
openshift-image-registry
openshift-infra
openshift-ingress
openshift-ingress-canary
openshift-ingress-operator
openshift-insights
openshift-kni-infra
openshift-kube-apiserver
openshift-kube-apiserver-operator
openshift-kube-controller-manager
openshift-kube-controller-manager-operator
openshift-kube-scheduler
openshift-kube-scheduler-operator
openshift-kube-storage-version-migrator
openshift-kube-storage-version-migrator-operator
openshift-machine-api
openshift-machine-config-operator
openshift-marketplace
openshift-monitoring
openshift-multus
openshift-network-diagnostics
openshift-network-operator
openshift-node
openshift-oauth-apiserver
openshift-openstack-infra
openshift-operator-lifecycle-manager
openshift-operators
openshift-ovirt-infra
openshift-sdn
openshift-service-ca
openshift-service-ca-operator
openshift-user-workload-monitoring
openshift-vsphere-infra
oc version
Client Version: v4.2.0-alpha.0-1292-g93bc841
Server Version: 4.10.0-0.ci.test-2021-12-08-210846-ci-op-7k5l72b7-latest
Kubernetes Version: v1.22.1-1757+6859754c3ffc75-dirty
docker version
/bin/bash: line 14: docker: command not found
podman version
/bin/bash: line 16: podman: command not found

pwd
/go/src/github.com/redhat-cne/cloud-event-proxy
go version go1.17.3 linux/amd64

GOROOT is:
/usr/local/go
GOROOT is:
/tmp/go

hich: no kustomize in (/tmp/go/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/local/go/bin:/go/bin:/cli)
SUITE=./test/cne hack/run-functests.sh
+ which ginkgo
which: no ginkgo in (/tmp/go/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/local/go/bin:/go/bin:/cli)
+ '[' 1 -ne 0 ']'
++ mktemp -d
+ GINKGO_TMP_DIR=/tmp/tmp.Gkt92LI9ZA
+ cd /tmp/tmp.Gkt92LI9ZA
+ go mod init tmp
go: creating new go.mod: module tmp
+ go get github.com/onsi/ginkgo/ginkgo@v1.14.1
go: downloading github.com/onsi/ginkgo v1.14.1
go: downloading golang.org/x/sys v0.0.0-20200519105757-fe76b779f299
go: downloading github.com/nxadm/tail v1.4.4
go get: installing executables with 'go get' in module mode is deprecated.
	To adjust and download dependencies of the current module, use 'go get -d'.
	To install using requirements of the current module, use 'go install'.
	To install ignoring the current module, use 'go install' with a version,
	like 'go install example.com/cmd@latest'.
	For more information, see https://golang.org/doc/go-get-install-deprecation
	or run 'go help get' or 'go help install'.
# golang.org/x/sys/internal/unsafeheader
compile: version "go1.15.15" does not match go tool version "go1.17.3"
# encoding
compile: version "go1.15.15" does not match go tool version "go1.17.3"
# unicode/utf16
compile: version "go1.15.15" does not match go tool version "go1.17.3"
# math/bits
compile: version "go1.15.15" does not match go tool version "go1.17.3"
# unicode/utf8
compile: version "go1.15.15" does not match go tool version "go1.17.3"
# internal/race
compile: version "go1.15.15" does not match go tool version "go1.17.3"
# runtime/internal/sys
compile: version "go1.15.15" does not match go tool version "go1.17.3"
# container/list
compile: version "go1.15.15" does not match go tool version "go1.17.3"
# internal/unsafeheader
compile: version "go1.15.15" does not match go tool version "go1.17.3"
# unicode
compile: version "go1.15.15" does not match go tool version "go1.17.3"
# internal/goversion
compile: version "go1.15.15" does not match go tool version "go1.17.3"
# internal/nettrace
compile: version "go1.15.15" does not match go tool version "go1.17.3"
# crypto/internal/subtle
compile: version "go1.15.15" does not match go tool version "go1.17.3"
# vendor/golang.org/x/crypto/cryptobyte/asn1
compile: version "go1.15.15" does not match go tool version "go1.17.3"
# vendor/golang.org/x/crypto/internal/subtle
compile: version "go1.15.15" does not match go tool version "go1.17.3"
# crypto/subtle
compile: version "go1.15.15" does not match go tool version "go1.17.3"
# runtime/internal/atomic
flag provided but not defined: -compiling-runtime
usage: asm [options] file.s ...
Flags:
  -D value
    	predefined symbol with optional simple value -D=identifier=value; can be set multiple times
  -I value
    	include directory; can be set multiple times
  -S	print assembly and machine code
  -V	print version and exit
  -debug
    	dump instructions as they are parsed
  -dynlink
    	support references to Go symbols defined in other shared libraries
  -e	no limit on number of errors reported
  -gensymabis
    	write symbol ABI information to output file, don't assemble
  -go115newobj
    	use new object file format (default true)
  -o string
    	output file; default foo.o for /a/b/c/foo.s as first argument
  -p string
    	set expected package import to path
  -shared
    	generate code that can be linked into a shared library
  -spectre list
    	enable spectre mitigations in list (all, ret)
  -trimpath string
    	remove prefix from recorded source file paths
# internal/cpu
compile: version "go1.15.15" does not match go tool version "go1.17.3"
# sync/atomic
compile: version "go1.15.15" does not match go tool version "go1.17.3"
# runtime/cgo
compile: version "go1.15.15" does not match go tool version "go1.17.3"
+ rm -rf /tmp/tmp.Gkt92LI9ZA
+ echo 'Downloading ginkgo tool'
Downloading ginkgo tool
+ cd -
/go/src/github.com/redhat-cne/cloud-event-proxy
+ GOPATH=/go
+ JUNIT_OUTPUT=/tmp/artifacts/unit_report.xml
+ export PATH=/tmp/go/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/local/go/bin:/go/bin:/cli:/go/bin
+ PATH=/tmp/go/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/local/go/bin:/go/bin:/cli:/go/bin
+ GOFLAGS=-mod=vendor
+ ginkgo ./test/cne -- -junit /tmp/artifacts/unit_report.xml
hack/run-functests.sh: line 21: ginkgo: command not found
make: *** [functests] Error 127

```


## Github Openshift CI 

Here's the site with all the documentation about the Github CI lanes that prow runs based on the openshift/release configuration: https://docs.ci.openshift.org/docs/

make ci-operator-config

## Rerun failed jobs
```
/retest or /test $NAME
```
the former will rerun all failed jobs, the latter just the one selected

## Trouble Shooting
```
{"component":"entrypoint","file":"prow/entrypoint/run.go:169","func":"k8s.io/test-infra/prow/entrypoint.Options.ExecuteProcess","level":"error","msg":"Entrypoint received interrupt: terminated","severity":"error","time":"2021-10-21T21:29:45Z"}
{"component":"entrypoint","file":"prow/entrypoint/run.go:252","func":"k8s.io/test-infra/prow/entrypoint.gracefullyTerminate","level":"error","msg":"Process gracefully exited before 1h0m0s grace period","severity":"error","time":"2021-10-21T21:29:45Z"}
```
That's a job that was interrupted because you pushed a new revision to that PR

## Openshift Release change
```
/home/jackding/repo/openshift/release

$ make new-repo
Enter the organization for the repository: redhat-cne
Enter the repository to initialize: hw-event-proxy
Enter the development branch for the repository: [default: master] main

Now, let's determine how the repository builds output artifacts...
Does the repository build and promote container images?  [default: no] yes
Does the repository promote images as part of the OpenShift release?  [default: no] yes
Do any images build on top of the OpenShift base image?  [default: no] 
Do any images build on top of the CentOS base image?  [default: no] 

Now, let's configure how the repository is compiled...
What version of Go does the repository build with? [default: 1.13] 1.16
[OPTIONAL] Enter the Go import path for the repository if it uses a vanity URL (e.g. "k8s.io/my-repo"): 
[OPTIONAL] What commands are used to build binaries in the repository? (e.g. "go install ./cmd/...") scripts/build-go.sh
[OPTIONAL] What commands are used to build test binaries? (e.g. "go install -race ./cmd/..." or "go test -c ./test/...") 

Are there any test scripts to configure?  [default: no] 

Are there any end-to-end test scripts to configure?  [default: no] yes
What is the name of this test (e.g. "e2e-operator")?  e2e-basic
Which specific cloud provider does the test require, if any?  [default: aws] 
What commands in the repository run the test (e.g. "make test-e2e")?  |
        # Make kubectl available by creating a symlink to oc.
        pushd "$CLI_DIR"
        if [ ! -f kubectl ]; then
            ln -s oc kubectl
        fi
        popd
        export VERSION=latest
        make test-ci


Does your test require the OpenShift client (oc)?  [default: no] yes
Are there any more end-to-end test scripts to configure?  [default: no] 


sudo chown -R jackding ci-operator/config/redhat-cne/hw-event-proxy/ ci-operator/jobs/redhat-cne/hw-event-proxy/ core-services/prow/02_config/redhat-cne/hw-event-proxy/

```