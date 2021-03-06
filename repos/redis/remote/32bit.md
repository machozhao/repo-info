## `redis:32bit`

```console
$ docker pull redis@sha256:944b998067bc435837421f69b554d38cc2e380b324c41b69d2a3ab1180c4dcb8
```

-	Platforms:
	-	linux; amd64

### `redis:32bit` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **77.9 MB (77895451 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a858c9b45e26bfd0a500a35b5ce32086cebd03811e870c75be84828857695c17`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Wed, 09 Nov 2016 01:00:56 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Wed, 09 Nov 2016 01:01:08 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 09 Nov 2016 01:01:09 GMT
ENV GOSU_VERSION=1.7
# Wed, 09 Nov 2016 01:01:13 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Wed, 09 Nov 2016 01:01:14 GMT
ENV REDIS_VERSION=3.2.5
# Wed, 09 Nov 2016 01:01:14 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-3.2.5.tar.gz
# Wed, 09 Nov 2016 01:01:14 GMT
ENV REDIS_DOWNLOAD_SHA1=6f6333db6111badaa74519d743589ac4635eba7a
# Wed, 09 Nov 2016 01:03:13 GMT
RUN apt-get update && apt-get install -y libc6-i386 --no-install-recommends && rm -rf /var/lib/apt/lists/*
# Wed, 09 Nov 2016 01:04:10 GMT
RUN set -ex 		&& buildDeps=' 		gcc 		gcc-multilib 		libc6-dev-i386 		make 	' 	&& apt-get update 	&& apt-get install -y $buildDeps --no-install-recommends 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL" 	&& echo "$REDIS_DOWNLOAD_SHA1 *redis.tar.gz" | sha1sum -c - 	&& mkdir -p /usr/src/redis 	&& tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1 	&& rm redis.tar.gz 		&& grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h 	&& sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h 	&& grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h 		&& make -C /usr/src/redis 32bit 	&& make -C /usr/src/redis install 		&& rm -r /usr/src/redis 		&& apt-get purge -y --auto-remove $buildDeps
# Wed, 09 Nov 2016 01:04:11 GMT
RUN mkdir /data && chown redis:redis /data
# Wed, 09 Nov 2016 01:04:11 GMT
VOLUME [/data]
# Wed, 09 Nov 2016 01:04:11 GMT
WORKDIR /data
# Wed, 09 Nov 2016 01:04:12 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Wed, 09 Nov 2016 01:04:12 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 09 Nov 2016 01:04:13 GMT
EXPOSE 6379/tcp
# Wed, 09 Nov 2016 01:04:13 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:769149e3a45cf39c61e1d814263c71759a0c71d2850079ce3ab9ea2512f0dfef`  
		Last Modified: Wed, 09 Nov 2016 01:02:20 GMT  
		Size: 2.0 KB (2044 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f43b3c0854aeb84067088fba78133a0dd2f6e358c606d800919b7c0b63f46c9`  
		Last Modified: Wed, 09 Nov 2016 01:02:22 GMT  
		Size: 16.6 MB (16609652 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70e928127ad85d3e1a54033603b6d4d3408df15fa4c41abc0c8caf6c2d26f07c`  
		Last Modified: Wed, 09 Nov 2016 01:02:18 GMT  
		Size: 807.9 KB (807934 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8122e57942548d426a56275a2a9f1050ad53dd445326a39aa83dacdf6098f637`  
		Last Modified: Wed, 09 Nov 2016 01:04:26 GMT  
		Size: 4.2 MB (4224695 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6d3cab49f269e5ba4ba10a9269d73e966ed3ed5328e92b06d36b8d6e14167d75`  
		Last Modified: Wed, 09 Nov 2016 01:04:27 GMT  
		Size: 4.9 MB (4893645 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:54ba26dfc2c8cce06d68bf02d58ced2570b98b33d6608828aca703acea660c84`  
		Last Modified: Wed, 09 Nov 2016 01:04:24 GMT  
		Size: 95.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3102e09b9fac69ec774878474bee62ffe757b68c27a5e043ccbf8c8753334b0c`  
		Last Modified: Wed, 09 Nov 2016 01:04:24 GMT  
		Size: 397.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
