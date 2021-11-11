# Linux containers

In linux you have containers, with them you can have multiple linux distros without taking performance hits.

## LXC 

lxc its a method to create containers in linux.

### Instructions

lxd is a manager for containers via lxc.
```bash
#Install with (it will install needed dependencies like the lxc):

# for arch
pacman -S lxd


# then you search for you distrubution
#for ubuntu you can do:
lxc image list ubuntu:
#and for others you can list with
lxc image list images:
#and it will give you a list of containers
#you can filter them with grep

# after um find what you need you can install it with the launch
# for exemple you can install archlinux with
lxc launch images:archlinux
# debian with
lxc launch images:debian/sid
#and ubuntu with
lxc launch ubuntu:20.04
# it will give you a name you change it with the move command if want to

#for using the console use the
lxc exec <name-of-the-container> bash

#for setting up an shared folder
lxc config device add <container-name> vartest disk source=$(pwd)/debian-shared path=/mnt/host

```




[after that setup ssh](https://www.freecodecamp.org/news/the-ultimate-guide-to-ssh-setting-up-ssh-keys/
)

to have ssh and passthrough the Xorg with
```bash
ssh -X <user>@<host>
```



for other stuff visit the 
[lxc](https://wiki.archlinux.org/title/Linux_Containers) 
and 
[lxd](https://wiki.archlinux.org/title/LXD) 
archwikis.

