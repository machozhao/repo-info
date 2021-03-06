## `golang:1-alpine`

```console
$ docker pull golang@sha256:25ad25d8bece9d403be107b07c86fb6b2b588a5b26133baa9d1215c07bdbfa39
```

-	Platforms:
	-	linux; amd64

### `golang:1-alpine` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **73.3 MB (73275541 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4e874ba5240682d53411752d2186e74418a9d33d04238ef07b19e7a09db7eeda`

```dockerfile
# Tue, 18 Oct 2016 20:31:22 GMT
ADD file:7afbc23fda8b0b3872623c16af8e3490b2cee951aed14b3794389c2f946cc8c7 in / 
# Tue, 18 Oct 2016 20:32:36 GMT
RUN apk add --no-cache ca-certificates
# Wed, 19 Oct 2016 21:55:10 GMT
ENV GOLANG_VERSION=1.7.3
# Wed, 19 Oct 2016 21:55:10 GMT
ENV GOLANG_SRC_URL=https://golang.org/dl/go1.7.3.src.tar.gz
# Wed, 19 Oct 2016 21:55:11 GMT
ENV GOLANG_SRC_SHA256=79430a0027a09b0b3ad57e214c4c1acfdd7af290961dd08d322818895af1ef44
# Wed, 19 Oct 2016 21:55:11 GMT
COPY file:b54d7d4313a41e3729d6f4b7aa6e6f33a1e99759cb2a04149fae89f8211c3a65 in / 
# Wed, 19 Oct 2016 21:56:10 GMT
RUN set -ex 	&& apk add --no-cache --virtual .build-deps 		bash 		gcc 		musl-dev 		openssl 		go 		&& export GOROOT_BOOTSTRAP="$(go env GOROOT)" 		&& wget -q "$GOLANG_SRC_URL" -O golang.tar.gz 	&& echo "$GOLANG_SRC_SHA256  golang.tar.gz" | sha256sum -c - 	&& tar -C /usr/local -xzf golang.tar.gz 	&& rm golang.tar.gz 	&& cd /usr/local/go/src 	&& patch -p2 -i /no-pic.patch 	&& ./make.bash 		&& rm -rf /*.patch 	&& apk del .build-deps
# Wed, 19 Oct 2016 21:56:10 GMT
ENV GOPATH=/go
# Wed, 19 Oct 2016 21:56:11 GMT
ENV PATH=/go/bin:/usr/local/go/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 19 Oct 2016 21:56:12 GMT
RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"
# Wed, 19 Oct 2016 21:56:12 GMT
WORKDIR /go
# Wed, 19 Oct 2016 21:56:12 GMT
COPY file:f6191f2c86edc9343569339f101facba47e886e33e29d70da6916ca6b1101a53 in /usr/local/bin/ 
```

-	Layers:
	-	`sha256:3690ec4760f95690944da86dc4496148a63d85c9e3100669a318110092f6862f`  
		Last Modified: Tue, 18 Oct 2016 20:32:39 GMT  
		Size: 2.3 MB (2312958 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c311f66f3ac9a1d4b9fdfa8ac09821993c24d540e6147d25793c861c67892238`  
		Last Modified: Tue, 18 Oct 2016 20:36:01 GMT  
		Size: 344.0 KB (343962 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4d1bd6f06a512616af4cc963a6a480772417ae6454ddd3449bb322a0c0f7f641`  
		Last Modified: Wed, 19 Oct 2016 22:01:02 GMT  
		Size: 438.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:303de2b017481f849acabcedfcd72acd64a9b9fe01ac390d22d745124c878cfc`  
		Last Modified: Wed, 19 Oct 2016 22:01:26 GMT  
		Size: 70.6 MB (70616711 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9e14a610b962f19fdf5ed742d2d73dd9e0032bb653c6aa4fdbcae4e3156d686b`  
		Last Modified: Wed, 19 Oct 2016 22:01:02 GMT  
		Size: 123.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b8c4ac4e92604b79006337436a5b5028212cf8b7bc1dfbd82d68f7034ca03eb`  
		Last Modified: Wed, 19 Oct 2016 22:01:02 GMT  
		Size: 1.3 KB (1349 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
