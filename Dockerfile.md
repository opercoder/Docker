### Example of the Dockerfile:
``` bash
FROM ubuntu:latest
RUN apt-get update; apt-get -y install fortune
ADD fortuneloop.sh /bin/fortuneloop.sh
ENTRYPOINT ["/bin/fortuneloop.sh"]
CMD ["10"] // argument by default
```
/bin/fortuneloop.sh:  
> #!/bin/bash  
trap "exit" SIGINT  
INTERVAL=$1  
echo Configured to generate new fortune every $INTERVAL seconds  
mkdir -p /var/htdocs  
while :  
do  
  echo $() Writing fortune to /var/htdocs/index.html  
  /usr/games/fortune > /var/htdocs/index.html  
  sleep $INTERVAL  
done  
