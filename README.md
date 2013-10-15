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
