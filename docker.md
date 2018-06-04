### commit a container to docker images
``` docker commit <container id> <image name>:<optional tag>```

### jupyter notebook
``` jupyter notebook --ip 0.0.0.0 --no-browser --allow-root ```

### access the server
``` ssh root@example.com ```

# Send Dockerfile to your directory on DGX
rsync -avz ~/Desktop/Dockerfile your-i-number@dgx:/data/your-i-number/dockerfile/
rsync -avz ~/Desktop/apt.conf your-i-number@dgx:/data/your-i-number/dockerfile/

# Build image
cd /data/your-i-number/dockerfile/
nvidia-docker build -t [image_name] .
