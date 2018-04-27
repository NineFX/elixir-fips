# elixir-fips

FIPS 140-2 API-enabled Elixir containers

## Elixir installation

This container contains [Elixir](http://elixir-lang.org) configured on top of Erlang with `--enable-fips` for a [FIPS mode crypto application](http://erlang.org/documentation/doc-9.0-rc1/lib/crypto-4.0/doc/html/fips.html). The container builds on an [Alpine image compiled in FIPS mode](https://hub.docker.com/r/ninefx/alpine-fips/).


## Not FIPS compliant

This Docker image is not FIPS compliant. The OpenSSL FIPS Security Policy requires that "An independently acquired FIPS 140­-2 validated implementation of SHA­1 HMAC must be used for this digest verification." The SHA1 HMAC in this image is validated by a vanilla OpenSSL installation in the underlying `Dockerfile`. However, feel free to modify the underlying `Dockerfile` for use with a FIPS module you validate with your own FIPS 140-2 implementation.

The goal of this project is to provide a convenient image to build/test Erlang software in FIPS mode. It is not suitable for a production deployment when FIPS 140-2 compliance is required.