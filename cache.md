# Cache

## Introduction

Laravel provides a unified API for various caching systems. The cache configuration is located in the `.env` file. In this file you may specify which cache driver you would like used by default throughout your application. Laravel supports popular caching backends like [Memcached](http://memcached.org) and [Redis](http://redis.io) out of the box.

## Differences From Laravel

The Lumen cache drivers utilize the exact same code as the full Laravel cache drivers. Beyond configuration, there are no differences between using the cache in Lumen and using the cache in Laravel; therefore, please consult the [full Laravel documentation](https://laravel.com/docs/cache) for usage examples.

> **Note:** Before using the `Cache` facade, be sure you have uncommented the `$app->withFacades()` method call in your `bootstrap/app.php` file.

### Redis Support

Before using a Redis cache with Lumen, you will need to install the `predis/predis (~1.0)` and `illuminate/redis (5.3.*)` packages via Composer. Then, you should register the `Illuminate\Redis\RedisServiceProvider` in your `bootstrap/app.php` file.

If you have not called `$app->withEloquent()` in your `bootstrap/app.php` file, then you should call `$app->configure('database');` in the `bootstrap/app.php` file to ensure the Redis database configuration is properly loaded.
