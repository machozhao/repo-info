## `ruby:2-slim`

```console
$ docker pull ruby@sha256:c3456a8e45ff926656b4b6bfc90434ebd8135169fb1d32e153d2c3c10a4b8807
```

-	Platforms:
	-	linux; amd64

### `ruby:2-slim` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **97.5 MB (97502218 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e523958caea8cb2c3d2d4061ca3604916ce3222dc94fcead96db343962e4b8ca`
-	Default Command: `["irb"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Wed, 09 Nov 2016 01:15:26 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Wed, 09 Nov 2016 01:15:27 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Wed, 09 Nov 2016 01:15:28 GMT
ENV RUBY_MAJOR=2.3
# Wed, 09 Nov 2016 01:15:28 GMT
ENV RUBY_VERSION=2.3.1
# Wed, 09 Nov 2016 01:15:29 GMT
ENV RUBY_DOWNLOAD_SHA256=b87c738cb2032bf4920fef8e3864dc5cf8eae9d89d8d523ce0236945c5797dcd
# Wed, 09 Nov 2016 01:15:29 GMT
ENV RUBYGEMS_VERSION=2.6.8
# Wed, 09 Nov 2016 01:18:13 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.gz "https://cache.ruby-lang.org/pub/ruby/$RUBY_MAJOR/ruby-$RUBY_VERSION.tar.gz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.gz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xzf ruby.tar.gz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.gz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& ./configure --disable-install-doc 	&& make -j"$(nproc)" 	&& make install 		&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION"
# Wed, 09 Nov 2016 01:18:13 GMT
ENV BUNDLER_VERSION=1.13.6
# Wed, 09 Nov 2016 01:18:15 GMT
RUN gem install bundler --version "$BUNDLER_VERSION"
# Wed, 09 Nov 2016 01:18:15 GMT
ENV GEM_HOME=/usr/local/bundle
# Wed, 09 Nov 2016 01:18:15 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Wed, 09 Nov 2016 01:18:16 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 09 Nov 2016 01:18:17 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Wed, 09 Nov 2016 01:18:17 GMT
CMD ["irb"]
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
	-	`sha256:e635357d42cf2c232035218cc1b23d1b53629d18797e3ce09de06d8cd8c5f029`  
		Last Modified: Wed, 09 Nov 2016 01:18:41 GMT  
		Size: 35.6 MB (35551595 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:382aff325decc08460ec0840ee0ba0b881a1f4b2a99fdfc47dbed16506e98f6d`  
		Last Modified: Wed, 09 Nov 2016 01:18:29 GMT  
		Size: 612.6 KB (612587 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f1fe764fd27438bd01327b892d274296309944b25f1710e35f6f641f1d7b5172`  
		Last Modified: Wed, 09 Nov 2016 01:18:29 GMT  
		Size: 162.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
