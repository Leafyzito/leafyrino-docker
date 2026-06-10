Fork of to include the packages needed for Leafyrino.

## Ubuntu 22.04

First, build the Ubuntu 22.04 build environment docker image:  
`docker build -t chatterino-ubuntu-22.04-build -f Dockerfile_chatterino2-build-ubuntu-22.04 .`

(alternatively pull from `ghcr.io/chatterino/chatterino2-build-ubuntu-22.04:latest`)

Clone the Chatterino repo with all submodules (will note it as `/home/user/chatterino2` from now on), e.g. with `git clone --recurse-submodules https://github.com/Chatterino/chatterino2`

Build Chatterino in the docker image:

```sh
docker run \
    -v /home/user/chatterino2:/srv \
    -w /srv \
    --rm \
    chatterino-ubuntu-22.04-build '.CI/full-ubuntu-build.sh'
```

Now you'll have an executable you can use or package in `/home/user/chatterino2/build`

## Ubuntu 24.04

See the 22.04 instructions above and replace 22.04 with 24.04
