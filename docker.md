### commit a container to docker images
``` docker commit <container id> <image name>:<optional tag>```

### jupyter notebook
``` jupyter notebook --ip 0.0.0.0 --no-browser --allow-root ```

### access the server
``` ssh root@example.com ```

### Send Dockerfile to your directory on DGX
```
rsync -avz ~/Desktop/Dockerfile your-i-number@dgx:/data/your-i-number/dockerfile/
rsync -avz ~/Desktop/apt.conf your-i-number@dgx:/data/your-i-number/dockerfile/
```

### Build image
```
cd /data/your-i-number/dockerfile/
nvidia-docker build -t [image_name] .
```
### create a container from image
```
nvidia-docker run -it -d --name <container name> -p 8888:8888 -p 6006:6006 -v /home/i351756:/root/i351756/ \
-v /data/i351756/dev:/data/ <image id/name>  /bin/bash
```
```
docker run -it -d --name lstmtrain -p 1234:8888 -p 5678:6006 -v /home/i351756:/root/i351756 -v /data/i351756/dev:/data/ i351756_tess:alpha /bin/bash
```
### run the container created
``` docker exec -it <container name> /bin/bash ```

### run jupyter notebook
```
jupyter notebook --generate-config
jupyter notebook --ip 0.0.0.0 --no-browser --allow-root
# Then locally, enter <DNS address>:<port assigned> in the browser
```
### remove docker image
```
docker rmi <image:tag>
```
