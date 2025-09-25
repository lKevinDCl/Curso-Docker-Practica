# Build con otras arquitecturas

> docker buildx ls

NAME/NODE           DRIVER/ENDPOINT     STATUS    BUILDKIT   PLATFORMS
default             docker
 \_ default          \_ default         running   v0.23.2    linux/amd64 (+3), linux/arm64, linux/arm (+2), linux/ppc64le, (2 more)
desktop-linux*      docker
 \_ desktop-linux    \_ desktop-linux   running   v0.23.2    linux/amd64 (+3), linux/arm64, linux/arm (+2), linux/ppc64le, (2 more)

 > docker buildx create --name mybuilder --driver docker-container --bootstrap

 [+] Building 13.5s (1/1) FINISHED
 => [internal] booting buildkit                                                                       13.4s 
 => => pulling image moby/buildkit:buildx-stable-1                                                    11.6s
 => => creating container buildx_buildkit_mybuilder0                                                   1.9s
mybuilder

 >> docker buildx use mybuilder

 NAME/NODE           DRIVER/ENDPOINT     STATUS    BUILDKIT   PLATFORMS
mybuilder*          docker-container
 \_ mybuilder0       \_ desktop-linux   running   v0.24.0    linux/amd64 (+3), linux/arm64, linux/arm (+2), linux/ppc64le, (3 more)
default             docker
 \_ default          \_ default         running   v0.23.2    linux/amd64 (+3), linux/arm64, linux/arm (+2), linux/ppc64le, (2 more)
desktop-linux       docker
 \_ desktop-linux    \_ desktop-linux   running   v0.23.2    linux/amd64 (+3), linux/arm64, linux/arm (+2), linux/ppc64le, (2 more)


 >> docker buildx build --platform linux/amd64,linux/arm64,linux/arm/v7 -t ikevindci/cron-ticker-by-kevindc:gato --push .


docker buildx build --platform linux/amd64,linux/arm64,linux/arm/v7 -t ikevindci/cron-ticker-by-kevindc:gato --push .
[+] Building 0.1s (1/1) FINISHED                                                 docker-container:mybuilder
 => [internal] load build definition from Dockerfile                                                   0.1s
 => => transferring dockerfile: 2B                                                                     0.0s
ERROR: failed to build: failed to solve: failed to read dockerfile: open Dockerfile: no such file or directory

View build details: docker-desktop://dashboard/build/mybuilder/mybuilder0/5zxlo05dpw1etbq5lmvanswjn

