
# About #

tiller (and helm) for ARM32v7 arch (Raspberry Pi 3B running 32-bit OS for example).

Note that provided Dockerfile contains dockerhub autobuild custom actions required to automatically build ARM images.

# branches / tags #

- 'master' branch : 'latest' tag
- 'v2.12.3' : 'v2.12.3' tag


# manual build / push #

```
  git checkout v2.12.3
  # edit Dockerfile and comment line copying qemu-arm-static
  docker build -t alemansec/tiller-arm32v7:v2.12.3 .
  docker login
  docker push alemansec/tiller-arm32v7:v2.12.3
```

# kubernetes deployment #

```
  # 'tiller' service account previously created using kubectl
  helm init --service-account tiller --tiller-image=alemansec/tiller-arm32v7:v2.12.3
```

