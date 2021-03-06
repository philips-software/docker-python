<div align="center">

# Docker-python

![Build Docker images](https://github.com/philips-software/docker-python/workflows/Build%20Docker%20images/badge.svg)
![repolinter](https://github.com/philips-software/docker-python/workflows/repolinter/badge.svg)
[![Slack](https://philips-software-slackin.now.sh/badge.svg)](https://philips-software-slackin.now.sh)

This repo will contain docker images with _python_

</div>

## Docker images

Current versions available:
```
.
├── 3
│   ├── openjdk
│   │   └── Dockerfile
│   ├── tox
│   │   └── Dockerfile
│   └── vanilla
│       └── Dockerfile
```
## Usage

Images can be found on [https://hub.docker.com/r/philipssoftware/python/](https://hub.docker.com/r/philipssoftware/python/).

```
docker run philipssoftware/python:latest python --version
docker run philipssoftware/python:buster python --version
```

## Content

The images obviously contains Python, but also two other files:
- `REPO`
- `TAGS`

### REPO

This file has a url to the REPO with specific commit-sha of the build.
Example: 

```
$ docker run philipssoftware/python:buster cat REPO
https://github.com/philips-software/docker-python/tree/bbb5945481e1579c87293d16bbf5cd654f3da158
```

```
$ docker run philipssoftware/python:tox cat REPO
https://github.com/philips-software/docker-python/tree/eb0c55137fd741d5526de9e7ef5d15f69a9d5a56
```

### TAGS

This contains all the similar tags at the point of creation. 

```
$ docker run philipssoftware/python cat TAGS
python:buster python:latest
```


```
$ docker run philipssoftware/python:tox cat TAGS
python:tox python:tox-3 python:tox-3.20 python:tox-3.20.1
```

You can use this to pin down a version of the container from an existing development build for production. When using `python:buster` for development. This ensures that you've got all security updates in your build. If you want to pin the version of your image down for production, you can use this file inside of the container to look for the most specific tag, the last one.

## Why

> Why do we have our own docker image definitions?

We often need some tools in a container for checking some things. F.e. [jq](https://stedolan.github.io/jq/), [aws-cli](https://aws.amazon.com/cli/) and [curl](https://curl.haxx.se/).
We can install this every time we need a container, but having this baked into a container seems a better approach.

That's why we want our own docker file definitions.

## Issues

- If you have an issue: report it on the [issue tracker](https://github.com/philips-software/docker-node/issues)

## Author

- Jeroen Knoops <jeroen.knoops@philips.com>

## License

License is MIT. See [LICENSE file](LICENSE.md)

## Philips Forest

This module is part of the Philips Forest.

```
                                                     ___                   _
                                                    / __\__  _ __ ___  ___| |_
                                                   / _\/ _ \| '__/ _ \/ __| __|
                                                  / / | (_) | | |  __/\__ \ |_
                                                  \/   \___/|_|  \___||___/\__|  

                                                                 Infrastructure
```

Talk to the forestkeepers in the `docker-images`-channel on Slack.

[![Slack](https://philips-software-slackin.now.sh/badge.svg)](https://philips-software-slackin.now.sh)
