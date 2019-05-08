# packer-qemu
Docker image for building qemu images with packer

## Build qemu based image

    docker run --rm                                                                    \
      -e PACKER_LOG=1                                                                  \
      -e PACKER_LOG_PATH="packer-docker.log"                                           \
      -it                                                                              \
      --privileged                                                                     \
      --cap-add=ALL -v /lib/modules:/lib/modules                                       \
      -v `pwd`:/opt/                                                                   \
      -v $HOME/.ssh/id_rsa:/root/.ssh/id_rsa                                           \
      -w /opt/ goffinet/packer-qemu build centos7.json
