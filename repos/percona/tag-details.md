<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `percona`

-	[`percona:5.7.15`](#percona5715)
-	[`percona:5.7`](#percona57)
-	[`percona:5`](#percona5)
-	[`percona:latest`](#perconalatest)
-	[`percona:5.6.33`](#percona5633)
-	[`percona:5.6`](#percona56)
-	[`percona:5.5.52`](#percona5552)
-	[`percona:5.5`](#percona55)

## `percona:5.7.15`

```console
$ docker pull percona@sha256:fa748516037f498628ade9d41ff1d990de10122c823e5f1b28de129488bf6f48
```

-	Platforms:
	-	linux; amd64

### `percona:5.7.15` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **119.9 MB (119862011 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a08ffff3955b38351b8ebbf75892cae99d1bd5a20c6a57bae416632666558d96`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 19:18:43 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Tue, 08 Nov 2016 19:18:43 GMT
ENV GOSU_VERSION=1.7
# Tue, 08 Nov 2016 19:19:05 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 08 Nov 2016 19:19:06 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 08 Nov 2016 19:19:23 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:11:25 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Tue, 08 Nov 2016 23:11:26 GMT
RUN echo 'deb https://repo.percona.com/apt jessie main' > /etc/apt/sources.list.d/percona.list
# Tue, 08 Nov 2016 23:11:26 GMT
ENV PERCONA_MAJOR=5.7
# Tue, 08 Nov 2016 23:11:26 GMT
ENV PERCONA_VERSION=5.7.15-9-1.jessie
# Tue, 08 Nov 2016 23:11:51 GMT
RUN { 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password password 'unused'; 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		percona-server-server-$PERCONA_MAJOR=$PERCONA_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld
# Tue, 08 Nov 2016 23:11:52 GMT
RUN find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& myCnf="$(find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lE '^\[mysqld\]' 		| head -n1)" 	&& echo 'skip-host-cache\nskip-name-resolve' 		| awk '{ print } $1 == "[mysqld]" && c == 0 { c = 1; system("cat") }' "$myCnf" > /tmp/my.cnf 	&& mv /tmp/my.cnf "$myCnf"
# Tue, 08 Nov 2016 23:11:53 GMT
VOLUME [/var/lib/mysql /var/log/mysql]
# Tue, 08 Nov 2016 23:11:53 GMT
COPY file:9eb04476822a578333892824948d1b65db598c9338b74030dec17808b490c956 in /usr/local/bin/ 
# Tue, 08 Nov 2016 23:11:55 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Tue, 08 Nov 2016 23:11:55 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 08 Nov 2016 23:11:56 GMT
EXPOSE 3306/tcp
# Tue, 08 Nov 2016 23:11:56 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:827c8d62b3329a4c0383314b094be7373311ec9f9e3ece9ed1ac11daf1c78ec6`  
		Last Modified: Tue, 08 Nov 2016 19:22:48 GMT  
		Size: 2.0 KB (2044 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de135f87677c2da2fb3658881e66c3f659b3a00ae012160ed49915ff3d1a755e`  
		Last Modified: Tue, 08 Nov 2016 19:22:47 GMT  
		Size: 1.2 MB (1216457 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05822f26ca6ef64a54f3b0af22565d6e3343b63aaee3c44fb57ca9910b53b81e`  
		Last Modified: Tue, 08 Nov 2016 19:22:45 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad65f56a251e632bec5c0e3b0971a8aaf77c78dee0c336cd392457e1742bb6e8`  
		Last Modified: Tue, 08 Nov 2016 19:22:47 GMT  
		Size: 6.5 MB (6464457 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95f7455c9d4d1f6ee03648a1bfcab8e23529d76a8c48b4efbae9dff8469e8445`  
		Last Modified: Tue, 08 Nov 2016 23:12:12 GMT  
		Size: 4.7 KB (4716 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d306a7267d9bb9bd89484bbc39c2dcf88187359e236f71ee034ef3a74a224bb7`  
		Last Modified: Tue, 08 Nov 2016 23:12:09 GMT  
		Size: 211.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:777f8bcceb2bb8193757304605e690c93331f8c27b58ddf048e3703107481d96`  
		Last Modified: Tue, 08 Nov 2016 23:12:27 GMT  
		Size: 60.8 MB (60814294 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:53e8c32fe7b8368a5170bcd6e716976236f1b85eaf16feb2a947633dfb1066ef`  
		Last Modified: Tue, 08 Nov 2016 23:12:08 GMT  
		Size: 787.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c333042f89b3ad52a60c1da3f3f502beeff07188572d1bd06a422acfc186f488`  
		Last Modified: Tue, 08 Nov 2016 23:12:08 GMT  
		Size: 1.8 KB (1822 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b402494c8b165a771861eada1f387d9271a3d0920ecfe4f897400ec4d2c3e5e2`  
		Last Modified: Tue, 08 Nov 2016 23:12:08 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `percona:5.7`

```console
$ docker pull percona@sha256:fa748516037f498628ade9d41ff1d990de10122c823e5f1b28de129488bf6f48
```

-	Platforms:
	-	linux; amd64

### `percona:5.7` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **119.9 MB (119862011 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a08ffff3955b38351b8ebbf75892cae99d1bd5a20c6a57bae416632666558d96`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 19:18:43 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Tue, 08 Nov 2016 19:18:43 GMT
ENV GOSU_VERSION=1.7
# Tue, 08 Nov 2016 19:19:05 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 08 Nov 2016 19:19:06 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 08 Nov 2016 19:19:23 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:11:25 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Tue, 08 Nov 2016 23:11:26 GMT
RUN echo 'deb https://repo.percona.com/apt jessie main' > /etc/apt/sources.list.d/percona.list
# Tue, 08 Nov 2016 23:11:26 GMT
ENV PERCONA_MAJOR=5.7
# Tue, 08 Nov 2016 23:11:26 GMT
ENV PERCONA_VERSION=5.7.15-9-1.jessie
# Tue, 08 Nov 2016 23:11:51 GMT
RUN { 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password password 'unused'; 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		percona-server-server-$PERCONA_MAJOR=$PERCONA_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld
# Tue, 08 Nov 2016 23:11:52 GMT
RUN find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& myCnf="$(find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lE '^\[mysqld\]' 		| head -n1)" 	&& echo 'skip-host-cache\nskip-name-resolve' 		| awk '{ print } $1 == "[mysqld]" && c == 0 { c = 1; system("cat") }' "$myCnf" > /tmp/my.cnf 	&& mv /tmp/my.cnf "$myCnf"
# Tue, 08 Nov 2016 23:11:53 GMT
VOLUME [/var/lib/mysql /var/log/mysql]
# Tue, 08 Nov 2016 23:11:53 GMT
COPY file:9eb04476822a578333892824948d1b65db598c9338b74030dec17808b490c956 in /usr/local/bin/ 
# Tue, 08 Nov 2016 23:11:55 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Tue, 08 Nov 2016 23:11:55 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 08 Nov 2016 23:11:56 GMT
EXPOSE 3306/tcp
# Tue, 08 Nov 2016 23:11:56 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:827c8d62b3329a4c0383314b094be7373311ec9f9e3ece9ed1ac11daf1c78ec6`  
		Last Modified: Tue, 08 Nov 2016 19:22:48 GMT  
		Size: 2.0 KB (2044 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de135f87677c2da2fb3658881e66c3f659b3a00ae012160ed49915ff3d1a755e`  
		Last Modified: Tue, 08 Nov 2016 19:22:47 GMT  
		Size: 1.2 MB (1216457 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05822f26ca6ef64a54f3b0af22565d6e3343b63aaee3c44fb57ca9910b53b81e`  
		Last Modified: Tue, 08 Nov 2016 19:22:45 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad65f56a251e632bec5c0e3b0971a8aaf77c78dee0c336cd392457e1742bb6e8`  
		Last Modified: Tue, 08 Nov 2016 19:22:47 GMT  
		Size: 6.5 MB (6464457 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95f7455c9d4d1f6ee03648a1bfcab8e23529d76a8c48b4efbae9dff8469e8445`  
		Last Modified: Tue, 08 Nov 2016 23:12:12 GMT  
		Size: 4.7 KB (4716 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d306a7267d9bb9bd89484bbc39c2dcf88187359e236f71ee034ef3a74a224bb7`  
		Last Modified: Tue, 08 Nov 2016 23:12:09 GMT  
		Size: 211.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:777f8bcceb2bb8193757304605e690c93331f8c27b58ddf048e3703107481d96`  
		Last Modified: Tue, 08 Nov 2016 23:12:27 GMT  
		Size: 60.8 MB (60814294 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:53e8c32fe7b8368a5170bcd6e716976236f1b85eaf16feb2a947633dfb1066ef`  
		Last Modified: Tue, 08 Nov 2016 23:12:08 GMT  
		Size: 787.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c333042f89b3ad52a60c1da3f3f502beeff07188572d1bd06a422acfc186f488`  
		Last Modified: Tue, 08 Nov 2016 23:12:08 GMT  
		Size: 1.8 KB (1822 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b402494c8b165a771861eada1f387d9271a3d0920ecfe4f897400ec4d2c3e5e2`  
		Last Modified: Tue, 08 Nov 2016 23:12:08 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `percona:5`

```console
$ docker pull percona@sha256:fa748516037f498628ade9d41ff1d990de10122c823e5f1b28de129488bf6f48
```

-	Platforms:
	-	linux; amd64

### `percona:5` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **119.9 MB (119862011 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a08ffff3955b38351b8ebbf75892cae99d1bd5a20c6a57bae416632666558d96`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 19:18:43 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Tue, 08 Nov 2016 19:18:43 GMT
ENV GOSU_VERSION=1.7
# Tue, 08 Nov 2016 19:19:05 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 08 Nov 2016 19:19:06 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 08 Nov 2016 19:19:23 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:11:25 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Tue, 08 Nov 2016 23:11:26 GMT
RUN echo 'deb https://repo.percona.com/apt jessie main' > /etc/apt/sources.list.d/percona.list
# Tue, 08 Nov 2016 23:11:26 GMT
ENV PERCONA_MAJOR=5.7
# Tue, 08 Nov 2016 23:11:26 GMT
ENV PERCONA_VERSION=5.7.15-9-1.jessie
# Tue, 08 Nov 2016 23:11:51 GMT
RUN { 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password password 'unused'; 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		percona-server-server-$PERCONA_MAJOR=$PERCONA_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld
# Tue, 08 Nov 2016 23:11:52 GMT
RUN find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& myCnf="$(find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lE '^\[mysqld\]' 		| head -n1)" 	&& echo 'skip-host-cache\nskip-name-resolve' 		| awk '{ print } $1 == "[mysqld]" && c == 0 { c = 1; system("cat") }' "$myCnf" > /tmp/my.cnf 	&& mv /tmp/my.cnf "$myCnf"
# Tue, 08 Nov 2016 23:11:53 GMT
VOLUME [/var/lib/mysql /var/log/mysql]
# Tue, 08 Nov 2016 23:11:53 GMT
COPY file:9eb04476822a578333892824948d1b65db598c9338b74030dec17808b490c956 in /usr/local/bin/ 
# Tue, 08 Nov 2016 23:11:55 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Tue, 08 Nov 2016 23:11:55 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 08 Nov 2016 23:11:56 GMT
EXPOSE 3306/tcp
# Tue, 08 Nov 2016 23:11:56 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:827c8d62b3329a4c0383314b094be7373311ec9f9e3ece9ed1ac11daf1c78ec6`  
		Last Modified: Tue, 08 Nov 2016 19:22:48 GMT  
		Size: 2.0 KB (2044 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de135f87677c2da2fb3658881e66c3f659b3a00ae012160ed49915ff3d1a755e`  
		Last Modified: Tue, 08 Nov 2016 19:22:47 GMT  
		Size: 1.2 MB (1216457 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05822f26ca6ef64a54f3b0af22565d6e3343b63aaee3c44fb57ca9910b53b81e`  
		Last Modified: Tue, 08 Nov 2016 19:22:45 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad65f56a251e632bec5c0e3b0971a8aaf77c78dee0c336cd392457e1742bb6e8`  
		Last Modified: Tue, 08 Nov 2016 19:22:47 GMT  
		Size: 6.5 MB (6464457 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95f7455c9d4d1f6ee03648a1bfcab8e23529d76a8c48b4efbae9dff8469e8445`  
		Last Modified: Tue, 08 Nov 2016 23:12:12 GMT  
		Size: 4.7 KB (4716 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d306a7267d9bb9bd89484bbc39c2dcf88187359e236f71ee034ef3a74a224bb7`  
		Last Modified: Tue, 08 Nov 2016 23:12:09 GMT  
		Size: 211.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:777f8bcceb2bb8193757304605e690c93331f8c27b58ddf048e3703107481d96`  
		Last Modified: Tue, 08 Nov 2016 23:12:27 GMT  
		Size: 60.8 MB (60814294 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:53e8c32fe7b8368a5170bcd6e716976236f1b85eaf16feb2a947633dfb1066ef`  
		Last Modified: Tue, 08 Nov 2016 23:12:08 GMT  
		Size: 787.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c333042f89b3ad52a60c1da3f3f502beeff07188572d1bd06a422acfc186f488`  
		Last Modified: Tue, 08 Nov 2016 23:12:08 GMT  
		Size: 1.8 KB (1822 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b402494c8b165a771861eada1f387d9271a3d0920ecfe4f897400ec4d2c3e5e2`  
		Last Modified: Tue, 08 Nov 2016 23:12:08 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `percona:latest`

```console
$ docker pull percona@sha256:fa748516037f498628ade9d41ff1d990de10122c823e5f1b28de129488bf6f48
```

-	Platforms:
	-	linux; amd64

### `percona:latest` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **119.9 MB (119862011 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a08ffff3955b38351b8ebbf75892cae99d1bd5a20c6a57bae416632666558d96`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 19:18:43 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Tue, 08 Nov 2016 19:18:43 GMT
ENV GOSU_VERSION=1.7
# Tue, 08 Nov 2016 19:19:05 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 08 Nov 2016 19:19:06 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 08 Nov 2016 19:19:23 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:11:25 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Tue, 08 Nov 2016 23:11:26 GMT
RUN echo 'deb https://repo.percona.com/apt jessie main' > /etc/apt/sources.list.d/percona.list
# Tue, 08 Nov 2016 23:11:26 GMT
ENV PERCONA_MAJOR=5.7
# Tue, 08 Nov 2016 23:11:26 GMT
ENV PERCONA_VERSION=5.7.15-9-1.jessie
# Tue, 08 Nov 2016 23:11:51 GMT
RUN { 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password password 'unused'; 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		percona-server-server-$PERCONA_MAJOR=$PERCONA_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld
# Tue, 08 Nov 2016 23:11:52 GMT
RUN find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& myCnf="$(find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lE '^\[mysqld\]' 		| head -n1)" 	&& echo 'skip-host-cache\nskip-name-resolve' 		| awk '{ print } $1 == "[mysqld]" && c == 0 { c = 1; system("cat") }' "$myCnf" > /tmp/my.cnf 	&& mv /tmp/my.cnf "$myCnf"
# Tue, 08 Nov 2016 23:11:53 GMT
VOLUME [/var/lib/mysql /var/log/mysql]
# Tue, 08 Nov 2016 23:11:53 GMT
COPY file:9eb04476822a578333892824948d1b65db598c9338b74030dec17808b490c956 in /usr/local/bin/ 
# Tue, 08 Nov 2016 23:11:55 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Tue, 08 Nov 2016 23:11:55 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 08 Nov 2016 23:11:56 GMT
EXPOSE 3306/tcp
# Tue, 08 Nov 2016 23:11:56 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:827c8d62b3329a4c0383314b094be7373311ec9f9e3ece9ed1ac11daf1c78ec6`  
		Last Modified: Tue, 08 Nov 2016 19:22:48 GMT  
		Size: 2.0 KB (2044 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de135f87677c2da2fb3658881e66c3f659b3a00ae012160ed49915ff3d1a755e`  
		Last Modified: Tue, 08 Nov 2016 19:22:47 GMT  
		Size: 1.2 MB (1216457 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05822f26ca6ef64a54f3b0af22565d6e3343b63aaee3c44fb57ca9910b53b81e`  
		Last Modified: Tue, 08 Nov 2016 19:22:45 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad65f56a251e632bec5c0e3b0971a8aaf77c78dee0c336cd392457e1742bb6e8`  
		Last Modified: Tue, 08 Nov 2016 19:22:47 GMT  
		Size: 6.5 MB (6464457 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95f7455c9d4d1f6ee03648a1bfcab8e23529d76a8c48b4efbae9dff8469e8445`  
		Last Modified: Tue, 08 Nov 2016 23:12:12 GMT  
		Size: 4.7 KB (4716 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d306a7267d9bb9bd89484bbc39c2dcf88187359e236f71ee034ef3a74a224bb7`  
		Last Modified: Tue, 08 Nov 2016 23:12:09 GMT  
		Size: 211.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:777f8bcceb2bb8193757304605e690c93331f8c27b58ddf048e3703107481d96`  
		Last Modified: Tue, 08 Nov 2016 23:12:27 GMT  
		Size: 60.8 MB (60814294 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:53e8c32fe7b8368a5170bcd6e716976236f1b85eaf16feb2a947633dfb1066ef`  
		Last Modified: Tue, 08 Nov 2016 23:12:08 GMT  
		Size: 787.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c333042f89b3ad52a60c1da3f3f502beeff07188572d1bd06a422acfc186f488`  
		Last Modified: Tue, 08 Nov 2016 23:12:08 GMT  
		Size: 1.8 KB (1822 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b402494c8b165a771861eada1f387d9271a3d0920ecfe4f897400ec4d2c3e5e2`  
		Last Modified: Tue, 08 Nov 2016 23:12:08 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `percona:5.6.33`

```console
$ docker pull percona@sha256:a2851f61f0156a8c79049757740f2f8b711a53a722ecdb78c54adb7b69248ed8
```

-	Platforms:
	-	linux; amd64

### `percona:5.6.33` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **110.7 MB (110687087 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c8df04087187a144c7f000092f63cb754d7dea5d7db5ab0eb9f7a209a9b9a2eb`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 19:18:43 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Tue, 08 Nov 2016 19:18:43 GMT
ENV GOSU_VERSION=1.7
# Tue, 08 Nov 2016 19:19:05 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 08 Nov 2016 19:19:06 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 08 Nov 2016 19:19:23 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:11:25 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Tue, 08 Nov 2016 23:11:26 GMT
RUN echo 'deb https://repo.percona.com/apt jessie main' > /etc/apt/sources.list.d/percona.list
# Tue, 08 Nov 2016 23:14:55 GMT
ENV PERCONA_MAJOR=5.6
# Tue, 08 Nov 2016 23:14:55 GMT
ENV PERCONA_VERSION=5.6.33-79.0-1.jessie
# Tue, 08 Nov 2016 23:15:28 GMT
RUN { 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password password 'unused'; 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		percona-server-server-$PERCONA_MAJOR=$PERCONA_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld
# Tue, 08 Nov 2016 23:15:29 GMT
RUN find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& myCnf="$(find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lE '^\[mysqld\]' 		| head -n1)" 	&& echo 'skip-host-cache\nskip-name-resolve' 		| awk '{ print } $1 == "[mysqld]" && c == 0 { c = 1; system("cat") }' "$myCnf" > /tmp/my.cnf 	&& mv /tmp/my.cnf "$myCnf"
# Tue, 08 Nov 2016 23:15:29 GMT
VOLUME [/var/lib/mysql /var/log/mysql]
# Tue, 08 Nov 2016 23:15:30 GMT
COPY file:c38424786fef36048757ce9163e6884f3aadef4ecd3505a138402d64aac38c4e in /usr/local/bin/ 
# Tue, 08 Nov 2016 23:15:31 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Tue, 08 Nov 2016 23:15:32 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 08 Nov 2016 23:15:32 GMT
EXPOSE 3306/tcp
# Tue, 08 Nov 2016 23:15:33 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:827c8d62b3329a4c0383314b094be7373311ec9f9e3ece9ed1ac11daf1c78ec6`  
		Last Modified: Tue, 08 Nov 2016 19:22:48 GMT  
		Size: 2.0 KB (2044 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de135f87677c2da2fb3658881e66c3f659b3a00ae012160ed49915ff3d1a755e`  
		Last Modified: Tue, 08 Nov 2016 19:22:47 GMT  
		Size: 1.2 MB (1216457 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05822f26ca6ef64a54f3b0af22565d6e3343b63aaee3c44fb57ca9910b53b81e`  
		Last Modified: Tue, 08 Nov 2016 19:22:45 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad65f56a251e632bec5c0e3b0971a8aaf77c78dee0c336cd392457e1742bb6e8`  
		Last Modified: Tue, 08 Nov 2016 19:22:47 GMT  
		Size: 6.5 MB (6464457 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95f7455c9d4d1f6ee03648a1bfcab8e23529d76a8c48b4efbae9dff8469e8445`  
		Last Modified: Tue, 08 Nov 2016 23:12:12 GMT  
		Size: 4.7 KB (4716 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d306a7267d9bb9bd89484bbc39c2dcf88187359e236f71ee034ef3a74a224bb7`  
		Last Modified: Tue, 08 Nov 2016 23:12:09 GMT  
		Size: 211.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f133f85b086890c65ce85b9ef50dd98b1cf5194562fa9e528c52908226790a2`  
		Last Modified: Tue, 08 Nov 2016 23:16:00 GMT  
		Size: 51.6 MB (51638274 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bd35ed388bd2f38515efe238d2191d2c2e85d08b6ed0cb39bfcb3e8183465336`  
		Last Modified: Tue, 08 Nov 2016 23:15:44 GMT  
		Size: 1.9 KB (1887 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2336c86a6fb2357bab4068cfe3606d680ecf5b2295e14837911964ce861f37fb`  
		Last Modified: Tue, 08 Nov 2016 23:15:45 GMT  
		Size: 1.8 KB (1818 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a2d2a29b49baaec9ef1f46f1748e4903af1d233e7eabd363e6f35e61034cb48`  
		Last Modified: Tue, 08 Nov 2016 23:15:47 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `percona:5.6`

```console
$ docker pull percona@sha256:a2851f61f0156a8c79049757740f2f8b711a53a722ecdb78c54adb7b69248ed8
```

-	Platforms:
	-	linux; amd64

### `percona:5.6` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **110.7 MB (110687087 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c8df04087187a144c7f000092f63cb754d7dea5d7db5ab0eb9f7a209a9b9a2eb`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 19:18:43 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Tue, 08 Nov 2016 19:18:43 GMT
ENV GOSU_VERSION=1.7
# Tue, 08 Nov 2016 19:19:05 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 08 Nov 2016 19:19:06 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 08 Nov 2016 19:19:23 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:11:25 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Tue, 08 Nov 2016 23:11:26 GMT
RUN echo 'deb https://repo.percona.com/apt jessie main' > /etc/apt/sources.list.d/percona.list
# Tue, 08 Nov 2016 23:14:55 GMT
ENV PERCONA_MAJOR=5.6
# Tue, 08 Nov 2016 23:14:55 GMT
ENV PERCONA_VERSION=5.6.33-79.0-1.jessie
# Tue, 08 Nov 2016 23:15:28 GMT
RUN { 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password password 'unused'; 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		percona-server-server-$PERCONA_MAJOR=$PERCONA_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld
# Tue, 08 Nov 2016 23:15:29 GMT
RUN find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& myCnf="$(find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lE '^\[mysqld\]' 		| head -n1)" 	&& echo 'skip-host-cache\nskip-name-resolve' 		| awk '{ print } $1 == "[mysqld]" && c == 0 { c = 1; system("cat") }' "$myCnf" > /tmp/my.cnf 	&& mv /tmp/my.cnf "$myCnf"
# Tue, 08 Nov 2016 23:15:29 GMT
VOLUME [/var/lib/mysql /var/log/mysql]
# Tue, 08 Nov 2016 23:15:30 GMT
COPY file:c38424786fef36048757ce9163e6884f3aadef4ecd3505a138402d64aac38c4e in /usr/local/bin/ 
# Tue, 08 Nov 2016 23:15:31 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Tue, 08 Nov 2016 23:15:32 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 08 Nov 2016 23:15:32 GMT
EXPOSE 3306/tcp
# Tue, 08 Nov 2016 23:15:33 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:827c8d62b3329a4c0383314b094be7373311ec9f9e3ece9ed1ac11daf1c78ec6`  
		Last Modified: Tue, 08 Nov 2016 19:22:48 GMT  
		Size: 2.0 KB (2044 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de135f87677c2da2fb3658881e66c3f659b3a00ae012160ed49915ff3d1a755e`  
		Last Modified: Tue, 08 Nov 2016 19:22:47 GMT  
		Size: 1.2 MB (1216457 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05822f26ca6ef64a54f3b0af22565d6e3343b63aaee3c44fb57ca9910b53b81e`  
		Last Modified: Tue, 08 Nov 2016 19:22:45 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad65f56a251e632bec5c0e3b0971a8aaf77c78dee0c336cd392457e1742bb6e8`  
		Last Modified: Tue, 08 Nov 2016 19:22:47 GMT  
		Size: 6.5 MB (6464457 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95f7455c9d4d1f6ee03648a1bfcab8e23529d76a8c48b4efbae9dff8469e8445`  
		Last Modified: Tue, 08 Nov 2016 23:12:12 GMT  
		Size: 4.7 KB (4716 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d306a7267d9bb9bd89484bbc39c2dcf88187359e236f71ee034ef3a74a224bb7`  
		Last Modified: Tue, 08 Nov 2016 23:12:09 GMT  
		Size: 211.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f133f85b086890c65ce85b9ef50dd98b1cf5194562fa9e528c52908226790a2`  
		Last Modified: Tue, 08 Nov 2016 23:16:00 GMT  
		Size: 51.6 MB (51638274 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bd35ed388bd2f38515efe238d2191d2c2e85d08b6ed0cb39bfcb3e8183465336`  
		Last Modified: Tue, 08 Nov 2016 23:15:44 GMT  
		Size: 1.9 KB (1887 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2336c86a6fb2357bab4068cfe3606d680ecf5b2295e14837911964ce861f37fb`  
		Last Modified: Tue, 08 Nov 2016 23:15:45 GMT  
		Size: 1.8 KB (1818 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a2d2a29b49baaec9ef1f46f1748e4903af1d233e7eabd363e6f35e61034cb48`  
		Last Modified: Tue, 08 Nov 2016 23:15:47 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `percona:5.5.52`

```console
$ docker pull percona@sha256:beafc9895425a99a177de42c08a2f9df7537b71634b79f0540bdc4e2a36bc2d6
```

-	Platforms:
	-	linux; amd64

### `percona:5.5.52` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **103.4 MB (103445282 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4281742f8dc7f66048ff111210103b007b6667cbf17d85a17467c84e71b99ced`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 19:18:43 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Tue, 08 Nov 2016 19:18:43 GMT
ENV GOSU_VERSION=1.7
# Tue, 08 Nov 2016 19:19:05 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 08 Nov 2016 19:19:06 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 08 Nov 2016 19:19:23 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:11:25 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Tue, 08 Nov 2016 23:11:26 GMT
RUN echo 'deb https://repo.percona.com/apt jessie main' > /etc/apt/sources.list.d/percona.list
# Tue, 08 Nov 2016 23:13:22 GMT
ENV PERCONA_MAJOR=5.5
# Tue, 08 Nov 2016 23:13:22 GMT
ENV PERCONA_VERSION=5.5.52-rel38.3-1.jessie
# Tue, 08 Nov 2016 23:14:05 GMT
RUN { 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password password 'unused'; 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		percona-server-server-$PERCONA_MAJOR=$PERCONA_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld
# Tue, 08 Nov 2016 23:14:06 GMT
RUN find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& myCnf="$(find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lE '^\[mysqld\]' 		| head -n1)" 	&& echo 'skip-host-cache\nskip-name-resolve' 		| awk '{ print } $1 == "[mysqld]" && c == 0 { c = 1; system("cat") }' "$myCnf" > /tmp/my.cnf 	&& mv /tmp/my.cnf "$myCnf"
# Tue, 08 Nov 2016 23:14:06 GMT
VOLUME [/var/lib/mysql /var/log/mysql]
# Tue, 08 Nov 2016 23:14:07 GMT
COPY file:c38424786fef36048757ce9163e6884f3aadef4ecd3505a138402d64aac38c4e in /usr/local/bin/ 
# Tue, 08 Nov 2016 23:14:08 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Tue, 08 Nov 2016 23:14:09 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 08 Nov 2016 23:14:09 GMT
EXPOSE 3306/tcp
# Tue, 08 Nov 2016 23:14:10 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:827c8d62b3329a4c0383314b094be7373311ec9f9e3ece9ed1ac11daf1c78ec6`  
		Last Modified: Tue, 08 Nov 2016 19:22:48 GMT  
		Size: 2.0 KB (2044 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de135f87677c2da2fb3658881e66c3f659b3a00ae012160ed49915ff3d1a755e`  
		Last Modified: Tue, 08 Nov 2016 19:22:47 GMT  
		Size: 1.2 MB (1216457 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05822f26ca6ef64a54f3b0af22565d6e3343b63aaee3c44fb57ca9910b53b81e`  
		Last Modified: Tue, 08 Nov 2016 19:22:45 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad65f56a251e632bec5c0e3b0971a8aaf77c78dee0c336cd392457e1742bb6e8`  
		Last Modified: Tue, 08 Nov 2016 19:22:47 GMT  
		Size: 6.5 MB (6464457 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95f7455c9d4d1f6ee03648a1bfcab8e23529d76a8c48b4efbae9dff8469e8445`  
		Last Modified: Tue, 08 Nov 2016 23:12:12 GMT  
		Size: 4.7 KB (4716 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d306a7267d9bb9bd89484bbc39c2dcf88187359e236f71ee034ef3a74a224bb7`  
		Last Modified: Tue, 08 Nov 2016 23:12:09 GMT  
		Size: 211.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:492da21ed650318b78b759cca632095e5aa0bd8e69ce4acbab126216f4781386`  
		Last Modified: Tue, 08 Nov 2016 23:14:34 GMT  
		Size: 44.4 MB (44396472 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7904a1fb4b2cf2fe2451ae5d15cc56fe85da1d02f4289e31d685df8a0944425d`  
		Last Modified: Tue, 08 Nov 2016 23:14:21 GMT  
		Size: 1.9 KB (1888 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea7390e51bb5bfea76a06f67f86e35854f2d2bbfb68f159b52d813ffec2e6cac`  
		Last Modified: Tue, 08 Nov 2016 23:14:21 GMT  
		Size: 1.8 KB (1816 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:964ed45eebb546634e914c35e99b2e6c9233c03d404f3aa6849563c50d989c67`  
		Last Modified: Tue, 08 Nov 2016 23:14:25 GMT  
		Size: 118.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `percona:5.5`

```console
$ docker pull percona@sha256:beafc9895425a99a177de42c08a2f9df7537b71634b79f0540bdc4e2a36bc2d6
```

-	Platforms:
	-	linux; amd64

### `percona:5.5` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **103.4 MB (103445282 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4281742f8dc7f66048ff111210103b007b6667cbf17d85a17467c84e71b99ced`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 19:18:43 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Tue, 08 Nov 2016 19:18:43 GMT
ENV GOSU_VERSION=1.7
# Tue, 08 Nov 2016 19:19:05 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 08 Nov 2016 19:19:06 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 08 Nov 2016 19:19:23 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:11:25 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Tue, 08 Nov 2016 23:11:26 GMT
RUN echo 'deb https://repo.percona.com/apt jessie main' > /etc/apt/sources.list.d/percona.list
# Tue, 08 Nov 2016 23:13:22 GMT
ENV PERCONA_MAJOR=5.5
# Tue, 08 Nov 2016 23:13:22 GMT
ENV PERCONA_VERSION=5.5.52-rel38.3-1.jessie
# Tue, 08 Nov 2016 23:14:05 GMT
RUN { 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password password 'unused'; 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		percona-server-server-$PERCONA_MAJOR=$PERCONA_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld
# Tue, 08 Nov 2016 23:14:06 GMT
RUN find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& myCnf="$(find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lE '^\[mysqld\]' 		| head -n1)" 	&& echo 'skip-host-cache\nskip-name-resolve' 		| awk '{ print } $1 == "[mysqld]" && c == 0 { c = 1; system("cat") }' "$myCnf" > /tmp/my.cnf 	&& mv /tmp/my.cnf "$myCnf"
# Tue, 08 Nov 2016 23:14:06 GMT
VOLUME [/var/lib/mysql /var/log/mysql]
# Tue, 08 Nov 2016 23:14:07 GMT
COPY file:c38424786fef36048757ce9163e6884f3aadef4ecd3505a138402d64aac38c4e in /usr/local/bin/ 
# Tue, 08 Nov 2016 23:14:08 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Tue, 08 Nov 2016 23:14:09 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 08 Nov 2016 23:14:09 GMT
EXPOSE 3306/tcp
# Tue, 08 Nov 2016 23:14:10 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:827c8d62b3329a4c0383314b094be7373311ec9f9e3ece9ed1ac11daf1c78ec6`  
		Last Modified: Tue, 08 Nov 2016 19:22:48 GMT  
		Size: 2.0 KB (2044 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de135f87677c2da2fb3658881e66c3f659b3a00ae012160ed49915ff3d1a755e`  
		Last Modified: Tue, 08 Nov 2016 19:22:47 GMT  
		Size: 1.2 MB (1216457 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05822f26ca6ef64a54f3b0af22565d6e3343b63aaee3c44fb57ca9910b53b81e`  
		Last Modified: Tue, 08 Nov 2016 19:22:45 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad65f56a251e632bec5c0e3b0971a8aaf77c78dee0c336cd392457e1742bb6e8`  
		Last Modified: Tue, 08 Nov 2016 19:22:47 GMT  
		Size: 6.5 MB (6464457 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95f7455c9d4d1f6ee03648a1bfcab8e23529d76a8c48b4efbae9dff8469e8445`  
		Last Modified: Tue, 08 Nov 2016 23:12:12 GMT  
		Size: 4.7 KB (4716 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d306a7267d9bb9bd89484bbc39c2dcf88187359e236f71ee034ef3a74a224bb7`  
		Last Modified: Tue, 08 Nov 2016 23:12:09 GMT  
		Size: 211.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:492da21ed650318b78b759cca632095e5aa0bd8e69ce4acbab126216f4781386`  
		Last Modified: Tue, 08 Nov 2016 23:14:34 GMT  
		Size: 44.4 MB (44396472 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7904a1fb4b2cf2fe2451ae5d15cc56fe85da1d02f4289e31d685df8a0944425d`  
		Last Modified: Tue, 08 Nov 2016 23:14:21 GMT  
		Size: 1.9 KB (1888 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea7390e51bb5bfea76a06f67f86e35854f2d2bbfb68f159b52d813ffec2e6cac`  
		Last Modified: Tue, 08 Nov 2016 23:14:21 GMT  
		Size: 1.8 KB (1816 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:964ed45eebb546634e914c35e99b2e6c9233c03d404f3aa6849563c50d989c67`  
		Last Modified: Tue, 08 Nov 2016 23:14:25 GMT  
		Size: 118.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
