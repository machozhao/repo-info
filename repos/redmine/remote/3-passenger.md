## `redmine:3-passenger`

```console
$ docker pull redmine@sha256:6a3d97ce168ebf154139ba078545da42f9fbff78934c385729ef595a1687ae64
```

-	Platforms:
	-	linux; amd64

### `redmine:3-passenger` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **278.9 MB (278851100 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:078f6a1771c84107ab8a655bcf68f444deadea3df6bc8fe2e109e9ef392fc5fb`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["passenger","start"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Wed, 09 Nov 2016 01:15:26 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Wed, 09 Nov 2016 01:15:27 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Wed, 09 Nov 2016 01:22:47 GMT
ENV RUBY_MAJOR=2.2
# Wed, 09 Nov 2016 01:22:48 GMT
ENV RUBY_VERSION=2.2.5
# Wed, 09 Nov 2016 01:22:48 GMT
ENV RUBY_DOWNLOAD_SHA256=30c4b31697a4ca4ea0c8db8ad30cf45e6690a0f09687e5d483c933c03ca335e3
# Wed, 09 Nov 2016 01:22:48 GMT
ENV RUBYGEMS_VERSION=2.6.8
# Wed, 09 Nov 2016 01:25:22 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.gz "https://cache.ruby-lang.org/pub/ruby/$RUBY_MAJOR/ruby-$RUBY_VERSION.tar.gz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.gz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xzf ruby.tar.gz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.gz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& ./configure --disable-install-doc 	&& make -j"$(nproc)" 	&& make install 		&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION"
# Wed, 09 Nov 2016 01:25:22 GMT
ENV BUNDLER_VERSION=1.13.6
# Wed, 09 Nov 2016 01:25:23 GMT
RUN gem install bundler --version "$BUNDLER_VERSION"
# Wed, 09 Nov 2016 01:25:24 GMT
ENV GEM_HOME=/usr/local/bundle
# Wed, 09 Nov 2016 01:25:24 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Wed, 09 Nov 2016 01:25:24 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 09 Nov 2016 01:25:25 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Wed, 09 Nov 2016 01:25:26 GMT
CMD ["irb"]
# Thu, 10 Nov 2016 08:42:02 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Thu, 10 Nov 2016 08:42:12 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Thu, 10 Nov 2016 08:42:13 GMT
ENV GOSU_VERSION=1.7
# Thu, 10 Nov 2016 08:42:18 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Thu, 10 Nov 2016 08:42:18 GMT
ENV TINI_VERSION=v0.9.0
# Thu, 10 Nov 2016 08:42:22 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini.asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 10 Nov 2016 08:42:47 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		imagemagick 		libmysqlclient18 		libpq5 		libsqlite3-0 				bzr 		git 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 10 Nov 2016 08:42:47 GMT
ENV RAILS_ENV=production
# Thu, 10 Nov 2016 08:42:48 GMT
WORKDIR /usr/src/redmine
# Thu, 10 Nov 2016 08:42:48 GMT
ENV REDMINE_VERSION=3.3.1
# Thu, 10 Nov 2016 08:42:48 GMT
ENV REDMINE_DOWNLOAD_MD5=cb8aab3e03cae7d21d003a307e51c176
# Thu, 10 Nov 2016 08:42:53 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 10 Nov 2016 08:45:18 GMT
RUN buildDeps=' 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	' 	&& set -ex 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends 	&& rm -rf /var/lib/apt/lists/* 	&& bundle install --without development test 	&& for adapter in mysql2 postgresql sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 	done 	&& rm ./config/database.yml 	&& apt-get purge -y --auto-remove $buildDeps
# Thu, 10 Nov 2016 08:45:19 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 10 Nov 2016 08:45:19 GMT
COPY file:58d2440ac347219d708111ff008abc0f4ff8cb9201b7893105b66b0ccf0a2521 in / 
# Thu, 10 Nov 2016 08:45:20 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 10 Nov 2016 08:45:20 GMT
EXPOSE 3000/tcp
# Thu, 10 Nov 2016 08:45:21 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
# Thu, 10 Nov 2016 08:47:00 GMT
ENV PASSENGER_VERSION=5.0.30
# Thu, 10 Nov 2016 08:47:16 GMT
RUN buildDeps=' 		make 	' 	&& set -x 	&& apt-get update && apt-get install -y --no-install-recommends $buildDeps && rm -rf /var/lib/apt/lists/* 	&& gem install passenger --version "$PASSENGER_VERSION" 	&& apt-get purge -y --auto-remove $buildDeps
# Thu, 10 Nov 2016 08:47:17 GMT
RUN set -x 	&& passenger-config install-agent 	&& passenger-config install-standalone-runtime
# Thu, 10 Nov 2016 08:47:18 GMT
CMD ["passenger" "start"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ec2a19adcb601ac582ae2b2cec63a8fead8b8eff63c7c73ec8e1c34084b0b971`  
		Last Modified: Wed, 09 Nov 2016 01:18:32 GMT  
		Size: 10.0 MB (9980683 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b37dcb8e3fe13596bfd392dd2619f6dc9b79fd00aad288ee04f23a2f5a14ffee`  
		Last Modified: Wed, 09 Nov 2016 01:18:29 GMT  
		Size: 202.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f78d2c489f98a4792f8526515245ce3baae884835b0cdb426351e29c5bdc8195`  
		Last Modified: Wed, 09 Nov 2016 01:25:49 GMT  
		Size: 33.8 MB (33752496 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f6e5ee871f8a9fe89f054a0867503610aa88822e16377d2d276ef55f8ea99a62`  
		Last Modified: Wed, 09 Nov 2016 01:25:38 GMT  
		Size: 612.6 KB (612586 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b88029c071710de9784b601fdcf6181a5f28ea37426aace930f73c77b88c0f4f`  
		Last Modified: Wed, 09 Nov 2016 01:25:37 GMT  
		Size: 162.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:394abcac37a210759b4b9a698b626dd5696f67cf2a789b6e0c38084e5cf60c94`  
		Last Modified: Thu, 10 Nov 2016 08:45:38 GMT  
		Size: 2.0 KB (2042 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6369d03987052492f6d826638b7114a835d9448af824f06e51082e2dd5252dc3`  
		Last Modified: Thu, 10 Nov 2016 08:45:42 GMT  
		Size: 13.9 MB (13862403 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a68a26ff5291e2219015f68d54bfe169a1478ef733462fee4ab8edecb866162c`  
		Last Modified: Thu, 10 Nov 2016 08:45:37 GMT  
		Size: 807.9 KB (807935 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a807c5406af1c7b8679b9672ed88c6a27f35df299c14719d58bc01f795a64cc7`  
		Last Modified: Thu, 10 Nov 2016 08:45:35 GMT  
		Size: 7.1 KB (7119 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f1d658469c68ca85b306c4c8568370fde71cfc1ab77f8a791ecda2d20236a71`  
		Last Modified: Thu, 10 Nov 2016 08:46:10 GMT  
		Size: 58.2 MB (58190848 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f3e1a3498c3a1c2d8a7f697e814e4428fee8e10f182fd6ab1fa31e4cc4ec7ebf`  
		Last Modified: Thu, 10 Nov 2016 08:45:33 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46a2e9304dded11b7a5f5faa2bde80daccab62ec9921422ab1954e73a1d0b3cd`  
		Last Modified: Thu, 10 Nov 2016 08:45:34 GMT  
		Size: 2.4 MB (2372937 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:664496d1f5f38324d251d6b56605c1f37ad9eb13526372e0f0df91b4454eaa30`  
		Last Modified: Thu, 10 Nov 2016 08:45:50 GMT  
		Size: 75.8 MB (75774616 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2a834754783930e0313eff0d2d2df7be3d4e11e3161895ccc6691ba31583df73`  
		Last Modified: Thu, 10 Nov 2016 08:45:33 GMT  
		Size: 1.2 KB (1157 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:38ab1de3915b156b9ceb1617c4db1ad03ccf606701e1ff9104ad60d532de950d`  
		Last Modified: Thu, 10 Nov 2016 08:47:35 GMT  
		Size: 21.7 MB (21710033 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:19beb4c82833b2d3eb0c9ba8c4adfdf12a454f029b96947254bbf4d7f5085e93`  
		Last Modified: Thu, 10 Nov 2016 08:47:34 GMT  
		Size: 10.4 MB (10418761 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
