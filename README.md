# node-pm2-alpine

[![Docker Hub Link][docker-img]][docker-url]

Alpine-Linux-based, tiny Docker-container for Node.JS and PM2, forked from inadarei's original at https://github.com/inadarei/node-alpine.

Compare 78MB of this container with typical 500MB to 800MB sizes you get with Ubuntu- or CentOS-based images.

This version deploys the v4.4.0LTS release of Node.JS.

### PM2 Support

This fork deploys PM2 for process management. The original release provided by inadarei deploys runit for process management.

A volume is mapped to /opt/app/ and by default PM2 is setup to call app.js. To get a basic application started you could use the following command.

```
sudo docker run -v /path/to/my/code:/opt/app --name someapp node-pm2-alpine
``` 

If you've named your main script something different, you can specify the name through the $APP environment variable like so.

```
sudo docker run -e APP=mymainscript.js -v /path/to/my/code:/opt/app --name someapp node-pm2-alpine
```

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
[docker-url]: https://hub.docker.com/r/christomich/node-pm2-alpine/