###  Run a registry:
``` bash
docker run -d -p 5000:443 --restart=always --name registry \
 -v /mnt/disk/registry:/var/lib/registry \
 -v "$(pwd)"/certs:/certs \
 -e REGISTRY_HTTP_ADDR=0.0.0.0:443 \
 -e REGISTRY_HTTP_TLS_CERTIFICATE=/certs/registry.cert \
 -e REGISTRY_HTTP_TLS_KEY=/certs/registry.key \
 -e REGISTRY_HTTP_SECRET=123456 \
 registry:2
 ```

### Access from a docker on remote machine:
Copy certificate to /etc/docker/certs.d/my-registry.example.com:5000/ca.crt  
``` bash
docker tag ubuntu:latest registry.example.com:5000/ubuntu-local
docker push registry.example.com:5000/ubuntu-local
```
