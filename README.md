/istrav/
=======
Innovation Management Software (IMS)

istrav source code:
- istrav.com: https://github.com/trabur/istrav.com
- trabur.workers.dev: https://github.com/trabur/istrav-global
- istrav.net: https://github.com/trabur/istrav-platform-frontgate
- meta.istrav.net: https://github.com/trabur/istrav-platform-frontend
- istrav.istrav.dev: https://github.com/trabur/istrav-platform-backend
- istrav-load-balancer: https://github.com/trabur/istrav-load-balancer
- istrav.dev: https://github.com/trabur/istrav.dev
- istrav-headquarters: https://github.com/trabur/istrav-headquarters
- istrav.stream: https://github.com/trabur/istrav.stream

meta.istrav.net tech:
- svelte-kit
- materializecss

## about
Allows people to sign into a members area only network.

https://<social-group>.istrav.net

### run
```bash
# fetch deps
$ npm install

# development
$ npm run dev
```

### versioning
```bash
# check version
$ npm run id

# tag a vew version
$ npm version v0.0.14 --no-git-tag-version

# check everything in
$ git add . && git commit -m "version" && git push

# then check version tag in
$ git tag v0.0.14
$ git push --tags
```

### clear port
```bash
$ lsof -i tcp:3000
$ kill -9 PID
```