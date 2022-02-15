# bitcoin-docker

# Purpose
- Compile Bitcoin Core in Docker
- Bitcoin depends on C++17. It is hard to build it on relatively old but still supported distributions, such as CentOS 7.

# How to build?
- Go to deployment/docker/bitcoin-cpu-server
- Run ./docker_build.sh

# Note
- This is the standard Bitcoin Core. Not going to be able to mine a bitcoin :-)