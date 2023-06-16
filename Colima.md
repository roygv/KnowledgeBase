[Replace Docker desktop](https://jacobtomlinson.dev/posts/2022/goodbye-docker-desktop-for-mac-hello-colima/)

```
colima start [--cpu 4 --memory 8]  # After each restart
colima start [-a x86_64] # May be requied for M1 chip???
colima stop
```

Maybe for Mac chip ???:
```
#!/bin/bash

ARCH=arm64
VERSION=v0.10.4
curl -LO https://github.com/docker/buildx/releases/download/${VERSION}/buildx-${VERSION}.darwin-${ARCH}
mkdir -p ~/.docker/cli-plugins
mv buildx-${VERSION}.darwin-${ARCH} ~/.docker/cli-plugins/docker-buildx
chmod +x ~/.docker/cli-plugins/docker-buildx
docker buildx version
```
