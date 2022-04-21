## Terminator search
ctrl-shift-f

## .alias
```
export GO111MODULE=on

export GOPATH=$HOME/go
export PATH=$PATH:/usr/local/go/bin
export PATH="$GOPATH/bin:$HOME/bin:$PATH"
export PATH="${KREW_ROOT:-$HOME/.krew}/bin:$PATH"

# Dell cnfdd4
export REDFISH_USERNAME=root
export REDFISH_PASSWORD=calvin
export REDFISH_HOSTADDR=10.19.28.42

# HP cnfdb1
#export REDFISH_USERNAME=administrator
#export REDFISH_PASSWORD=password
#export REDFISH_HOSTADDR=10.19.28.20

# HP helix01
#export REDFISH_USERNAME=admin
#export REDFISH_PASSWORD=admin
#export REDFISH_HOSTADDR=10.46.61.155

# ZT QE
#export REDFISH_USERNAME=Administrator
#export REDFISH_PASSWORD=superuser
#export REDFISH_HOSTADDR=10.1.148.29

# helix28
#export REDFISH_HOSTADDR=10.46.61.213
# master2
#export REDFISH_HOSTADDR=10.1.189.22

export KUBECONFIG=~/.kube/config

alias cdcode='cd /home/jackding/repo/redhat-cne/hw-event-proxy'
alias cdnote='cd /home/jackding/repo/jzding/playground/notes'
alias cdci='cd /home/jackding/repo/openshift/release'
alias cdtest='cd /home/jackding/repo/jzding/hw-event-test'

# Labs, pass: unix1234
alias cnfdt15='ssh root@10.46.55.194'
alias cnfde7='ssh root@10.16.231.155'
alias cnfdd4='ssh root@10.19.17.47'

# Hypervisor, pass 123123
alias cnfdd1='ssh kni@10.19.16.98'

alias oclogin='oc login https://api.cnfdd4.t5g.lab.eng.bos.redhat.com:6443 -u=kubeadmin -p=4LdqA-uvS3z-wE64N-v3YS7'

```

# Fedora
## Install Software
```
sudo dnf install python3.6
sudo dnf install python3-devel.x86_64

sudo dnf in grub-customizer
sudo dnf install neofetch

sudo dnf install terminator
sudo dnf install slack

sudo dnf install golang
mkdir -p $HOME/go
echo 'export GOPATH=$HOME/go' >> $HOME/.bashrc

sudo dnf install yamllint

wget https://mirror.openshift.com/pub/openshift-v4/clients/ocp/stable/openshift-client-linux.tar.gz
tar -zxvf openshift-client-linux.tar.gz
sudo cp oc /usr/local/bin
sudo cp kubectl /usr/local/bin

# install kind
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.11.1/kind-linux-amd64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/

# install docker
sudo dnf -y install dnf-plugins-core
sudo dnf config-manager \
    --add-repo \
    https://download.docker.com/linux/fedora/docker-ce.repo
sudo dnf install docker-ce docker-ce-cli containerd.io

# start docker
sudo systemctl start docker

# install cli
sudo dnf -y copr enable karmab/kcli ; sudo dnf -y install kcli

sudo dnf -y install vim-enhanced

```


## remove screenshot sounds
```
sudo mv /usr/share/sounds/freedesktop/stereo/camera-shutter.oga /usr/share/sounds/freedesktop/stereo/camera-shutter.oga.bak
```

## Fix for Google Meeting screen sharing
With this fix you are able to share entire desktop instead of a single window.
Type this in the chrome to find the flag for "WebRTC PipeWire support" and enable it.
```
chrome://flags/#enable-webrtc-pipewire-capturer
```

# Windows