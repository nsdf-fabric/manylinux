# Generate Docker images with shared libraries 

See https://hub.docker.com/repositories

Run:

```
# this is for Docker Desktop to enable `docker buildx build`
export DOCKER_CLI_EXPERIMENTAL=enabled

# this is for the following push to docker hub
sudo docker login -u nsdf
# type the TOKEN here

# I am interested in these 
POLICY=manylinux2010 PLATFORM=x86_64   COMMIT_SHA=latest CI=true DOCKER_PREFIX=nsdf ./build.sh
POLICY=manylinux2014 PLATFORM=x86_64   COMMIT_SHA=latest CI=true DOCKER_PREFIX=nsdf ./build.sh
POLICY=manylinux2014 PLATFORM=aarch64  COMMIT_SHA=latest CI=true DOCKER_PREFIX=nsdf ./build.sh

sudo docker push nsdf/manylinux2010_x86_64:latest
sudo docker push nsdf/manylinux2014_x86_64:latest
sudo docker push nsdf/manylinux2014_aarch64:latest
```

