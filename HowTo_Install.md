## Podman to Ubuntu 20.04
#### 1. Add the kubic repository:
    echo "deb https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/xUbuntu_${VERSION_ID}/ /" | sudo tee /etc/apt/sources.list.d/devel:kubic:libcontainers:stable.list
#### 2. Add GPG Key:
    curl -L https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/xUbuntu_${VERSION_ID}/Release.key | sudo apt-key add -
#### 3. Update the package cache and upgrade the system:
    apt-get update && apt-get upgrade
#### 4. Install podman:
    apt-get install podman
    
    
