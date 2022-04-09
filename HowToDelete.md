#### 1. Check your version od Docker:
    dpkg -l | grep -i docker
#### 2. Delete Docker:
    sudo apt-get purge -y docker-engine docker docker.io docker-ce  
    sudo apt-get autoremove -y --purge docker-engine docker docker.io docker-ce  
#### 3. Delete all other Docker files:
    sudo rm -rf /var/lib/docker /etc/docker
    sudo rm /etc/apparmor.d/docker
    sudo groupdel docker
    sudo rm -rf /var/run/docker.sock
    sudo rm -rf /var/run/docker/
> If you can't delete _/var/run/docker/_, you must firstly umount nsfs:  
``` bash
mount | grep docker  
umount /run/docker/netns/default
```
