# heroku-buildpack-redis

A buildpack that installs redis.

## Use

The desired version of redis is specified via the `redis-version` file.

See [test-redis-app](https://github.com/dpiddy/test-redis-app) for an example.

## Example

```bash
$ git clone https://github.com/dpiddy/test-redis-app.git
$ cd test-redis-app
$ cat redis-version
2.6
$ heroku create -b https://github.com/dpiddy/heroku-buildpack-redis.git
$ git push heroku master
$ heroku scale redis=1
$ heroku logs -t
```

## Building redis

`redis-2.6.tgz` used by the buildpack was built with [anvil](https://github.com/ddollar/anvil-cli) using this command:

```bash
$ anvil build \
    http://download.redis.io/releases/redis-2.6.16.tar.gz \
    -b https://gist.github.com/dpiddy/5b5425d57396135f59b2/raw/gistfile1.txt
```

Other versions should be buildable just by changing the redis tarball URL.
