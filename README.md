# Redis Storage for [OAuth 2.0](https://github.com/printesoi/oauth2)

[![Build][Build-Status-Image]][Build-Status-Url] [![Codecov][codecov-image]][codecov-url] [![ReportCard][reportcard-image]][reportcard-url] [![GoDoc][godoc-image]][godoc-url] [![License][license-image]][license-url]

## Install

``` bash
$ go get -u -v github.com/printesoi/redis/v4
```

## Usage

``` go
package main

import (
	"github.com/redis/go-redis/v9"
	oredis "github.com/printesoi/redis/v4"
	"github.com/printesoi/oauth2/v4/manage"
)

func main() {
	manager := manage.NewDefaultManager()
	
	// use redis token store
	manager.MapTokenStorage(oredis.NewRedisStore(&redis.Options{
		Addr: "127.0.0.1:6379",
		DB: 15,
	}))

	// use redis cluster store
	// manager.MapTokenStorage(oredis.NewRedisClusterStore(&redis.ClusterOptions{
	// 	Addrs: []string{"127.0.0.1:6379"},
	// 	DB: 15,
	// }))
}
```

## MIT License

```
Copyright (c) 2020 Lyric
```

[Build-Status-Url]: https://travis-ci.org/printesoi/redis
[Build-Status-Image]: https://travis-ci.org/printesoi/redis.svg?branch=master
[codecov-url]: https://codecov.io/gh/printesoi/redis
[codecov-image]: https://codecov.io/gh/printesoi/redis/branch/master/graph/badge.svg
[reportcard-url]: https://goreportcard.com/report/github.com/printesoi/redis/v4
[reportcard-image]: https://goreportcard.com/badge/github.com/printesoi/redis/v4
[godoc-url]: https://godoc.org/github.com/printesoi/redis/v4
[godoc-image]: https://godoc.org/github.com/printesoi/redis/v4?status.svg
[license-url]: http://opensource.org/licenses/MIT
[license-image]: https://img.shields.io/npm/l/express.svg
