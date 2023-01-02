Build docker image (Building will take few hours)

```
export DOCKER_BUILDKIT=1
docker buildx create --use
docker build --platform linux/arm/v7 -t armv7-amule .
docker build --platform linux/arm64 -t arm64-amule .
cd arm-amule-docker
```
Push images to dockerhub
```
docker login
docker tag armv7-amule username/armv7-amule:latest
docker push username/armv7-amule:latest
docker tag arm64-amule username/arm64-amule:latest
docker push username/arm64-amule:latest
```
