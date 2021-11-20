# Lima Configuration Files for Docker-based Development

A collection of [Lima](https://github.com/lima-vm/lima) configuration files to support docker-based development.

## Using (macOS)

First, install Lima using Homebrew:

`brew install lima`

Start Lima using configuration:

`limactl start dockerd.yaml`

`limactl start containerd.yaml`

Configure socket (for dockerd):

`export DOCKER_HOST=unix://${HOME}/docker.sock`

or create alias (if using containerd):

`alias docker="lima nerdctl"`

## Testing

Simple build:

`docker pull ubuntu:latest`

`docker run -ti ubuntu:latest /bin/bash`

Test volume mounting (replace SRC with local path to mount in the container):

`docker run -v [SRC]:/mnt/tmp:rw -ti ubuntu:latest /bin/bash`




