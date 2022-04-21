## VIM
sudo dnf -y install vim-enhanced

## Graphical diff tool
meld

## Install Docker in Fedora
https://docs.docker.com/engine/install/fedora/

https://docs.docker.com/engine/install/linux-postinstall/

### Start docker
```
systemctl start docker
```


## Fix for Google Meeting screen sharing:
1. sudo vi /etc/gdm/custom.conf
2. unncomment the line: WaylandEnable=false
3. add the following line to the [deamon]section as well: DefaultSession=gnome-xorg.desktop
4. restart the laptop

## Misc
```
sudo dnf install gcc-c++
google-chrome --use-cmd-decoder=validating --use-gl=desktop
```