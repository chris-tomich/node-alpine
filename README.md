# node-alpine

[![Docker Hub Link][docker-img]][docker-url]
[![](https://badge.imagelayers.io/irakli/node-alpine:latest.svg)](https://imagelayers.io/?images=irakli/node-alpine:latest 'Node Alpine on Docker Hub')

Alpine-Linux-based, tiny Docker-container for Node, striving for perfection

Compare 56MB of this container with typical 500MB to 800MB sizes you get with Ubuntu- or CentOS-based images.

This version deploys the v4.4.0LTS release of Node.JS.

### PM2 Support

This fork deploys PM2 for process management. The original release provided by inadarei deploys runit for process management.

A volume is mapped to /opt/app/

## Adding More Packages (if needed)

If you need more packages installed (e.g. make, gcc for compiling some native Node modules, or imagemagick etc.) base your new container on this one and you can use `apk` package manager that Alpine provides. For instance:

```
apk search --update imagemagick
```

or:

```
apk add --update make gcc g++ python linux-header
```

## License

[MIT](LICENSE)

[docker-img]: https://img.shields.io/badge/docker-ready-blue.svg
[docker-url]: https://hub.docker.com/r/irakli/node-alpine/
