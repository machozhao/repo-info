## `wordpress:php5.6-fpm`

```console
$ docker pull wordpress@sha256:0ba8cac2fd65917f97806493b1eb1fc10d6b9c61fb134b35e30d28f31eecaad7
```

-	Platforms:
	-	linux; amd64

### `wordpress:php5.6-fpm` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **160.9 MB (160947797 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4fbb75356b8250b90c52637c6ef2c3fd6c5bec49cedc3fee4fc0e44d237c555c`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["php-fpm"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 23:16:24 GMT
ENV PHPIZE_DEPS=autoconf 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 08 Nov 2016 23:16:53 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		libedit2 		libsqlite3-0 		libxml2 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:16:54 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 08 Nov 2016 23:16:55 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 08 Nov 2016 23:26:13 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--enable-fpm --with-fpm-user=www-data --with-fpm-group=www-data
# Tue, 08 Nov 2016 23:26:13 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Tue, 08 Nov 2016 23:26:13 GMT
ENV PHP_VERSION=5.6.27
# Tue, 08 Nov 2016 23:26:14 GMT
ENV PHP_URL=https://secure.php.net/get/php-5.6.27.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-5.6.27.tar.xz.asc/from/this/mirror
# Tue, 08 Nov 2016 23:26:14 GMT
ENV PHP_SHA256=16eb544498339d1d855292826e2e547ab01a31600141094959073e5e10e93ab5 PHP_MD5=9ce6efc96d5ab81ef808f8ed6b1f242d
# Tue, 08 Nov 2016 23:26:25 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 08 Nov 2016 23:26:26 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 08 Nov 2016 23:30:10 GMT
RUN set -xe 	&& buildDeps=" 		$PHP_EXTRA_BUILD_DEPS 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 	" 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& docker-php-source extract 	&& cd /usr/src/php 	&& ./configure 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $buildDeps
# Tue, 08 Nov 2016 23:30:11 GMT
COPY multi:ed54b4fe7bef284934703fa6e979b7cc0daed0549a07586d0c1ccd4e2b41884a in /usr/local/bin/ 
# Tue, 08 Nov 2016 23:30:11 GMT
WORKDIR /var/www/html
# Tue, 08 Nov 2016 23:30:12 GMT
RUN set -ex 	&& cd /usr/local/etc 	&& if [ -d php-fpm.d ]; then 		sed 's!=NONE/!=!g' php-fpm.conf.default | tee php-fpm.conf > /dev/null; 		cp php-fpm.d/www.conf.default php-fpm.d/www.conf; 	else 		mkdir php-fpm.d; 		cp php-fpm.conf.default php-fpm.d/www.conf; 		{ 			echo '[global]'; 			echo 'include=etc/php-fpm.d/*.conf'; 		} | tee php-fpm.conf; 	fi 	&& { 		echo '[global]'; 		echo 'error_log = /proc/self/fd/2'; 		echo; 		echo '[www]'; 		echo '; if we send this to /proc/self/fd/1, it never appears'; 		echo 'access.log = /proc/self/fd/2'; 		echo; 		echo 'clear_env = no'; 		echo; 		echo '; Ensure worker stdout and stderr are sent to the main error log.'; 		echo 'catch_workers_output = yes'; 	} | tee php-fpm.d/docker.conf 	&& { 		echo '[global]'; 		echo 'daemonize = no'; 		echo; 		echo '[www]'; 		echo 'listen = [::]:9000'; 	} | tee php-fpm.d/zz-docker.conf
# Tue, 08 Nov 2016 23:30:12 GMT
EXPOSE 9000/tcp
# Tue, 08 Nov 2016 23:30:13 GMT
CMD ["php-fpm"]
# Thu, 10 Nov 2016 02:42:07 GMT
RUN apt-get update && apt-get install -y libpng12-dev libjpeg-dev && rm -rf /var/lib/apt/lists/* 	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr 	&& docker-php-ext-install gd mysqli opcache
# Thu, 10 Nov 2016 02:42:08 GMT
RUN { 		echo 'opcache.memory_consumption=128'; 		echo 'opcache.interned_strings_buffer=8'; 		echo 'opcache.max_accelerated_files=4000'; 		echo 'opcache.revalidate_freq=2'; 		echo 'opcache.fast_shutdown=1'; 		echo 'opcache.enable_cli=1'; 	} > /usr/local/etc/php/conf.d/opcache-recommended.ini
# Thu, 10 Nov 2016 02:42:08 GMT
VOLUME [/var/www/html]
# Thu, 10 Nov 2016 02:42:08 GMT
ENV WORDPRESS_VERSION=4.6.1
# Thu, 10 Nov 2016 02:42:09 GMT
ENV WORDPRESS_SHA1=027e065d30a64720624a7404a1820e6c6fff1202
# Thu, 10 Nov 2016 02:42:11 GMT
RUN set -x 	&& curl -o wordpress.tar.gz -fSL "https://wordpress.org/wordpress-${WORDPRESS_VERSION}.tar.gz" 	&& echo "$WORDPRESS_SHA1 *wordpress.tar.gz" | sha1sum -c - 	&& tar -xzf wordpress.tar.gz -C /usr/src/ 	&& rm wordpress.tar.gz 	&& chown -R www-data:www-data /usr/src/wordpress
# Thu, 10 Nov 2016 02:42:12 GMT
COPY file:edc5484a4fe2732599d330aa3fa262e223f936c97c5119cd00f8d2336584ba48 in /usr/local/bin/ 
# Thu, 10 Nov 2016 02:42:13 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat
# Thu, 10 Nov 2016 02:42:13 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 10 Nov 2016 02:42:13 GMT
CMD ["php-fpm"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:269e95c6053af006e565f05aa87acc36a1e1dbdf1a7ac29c0de4739bfc0e40ef`  
		Last Modified: Tue, 08 Nov 2016 23:21:22 GMT  
		Size: 77.6 MB (77591280 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6243d5c57a349bb65b8641277fdb52b01726cbeadf307cf33a0293e6a2a17f6c`  
		Last Modified: Tue, 08 Nov 2016 23:21:00 GMT  
		Size: 181.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4ad0b90fb0a5434c1eb5aa334b916b2167ed8b5d318f07d2fce14456916f6e68`  
		Last Modified: Tue, 08 Nov 2016 23:30:28 GMT  
		Size: 12.5 MB (12549832 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fa880017946bcc3ade05c9725a5f5bee2367c3bdda5bef6c07fc3c60649f37c1`  
		Last Modified: Tue, 08 Nov 2016 23:30:25 GMT  
		Size: 490.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c805a096fa0781b9ca95f6e1d58f806a79a57cd3ea0ca425ec37ec1167a6fb0b`  
		Last Modified: Tue, 08 Nov 2016 23:30:29 GMT  
		Size: 8.8 MB (8842367 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:300681c718926072d99ba21a13f266c7b472ba5e8e21fd0c949631dcb7c81d0e`  
		Last Modified: Tue, 08 Nov 2016 23:30:25 GMT  
		Size: 1.8 KB (1836 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:90d90e44a9a93d8841377523ae0709f8d98548eda24a81a6e80eef087173cf41`  
		Last Modified: Tue, 08 Nov 2016 23:30:24 GMT  
		Size: 127.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f0a7f9164166ac1581c420341bdb7322d098b06c78ff761c7e8a18a0c81a05a`  
		Last Modified: Tue, 08 Nov 2016 23:30:25 GMT  
		Size: 7.6 KB (7627 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eb197db41cd2dc38e46fa09961b0226a910097304aad85ac5a758d25df313166`  
		Last Modified: Thu, 10 Nov 2016 02:42:27 GMT  
		Size: 2.8 MB (2804147 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5521fe23c423ac9878eaa874df544fa808a9f432bfc51616642be6a764e40d0`  
		Last Modified: Thu, 10 Nov 2016 02:42:26 GMT  
		Size: 332.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:45783db138e5e00b9bb8159d38817388dc11a0e9a9ae459ad4c54580f85226e9`  
		Last Modified: Thu, 10 Nov 2016 02:42:29 GMT  
		Size: 7.8 MB (7789791 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8593f95ce2f23746b0b01c42be2040cc0613873f477e2f9e2370fbf7d89f1641`  
		Last Modified: Thu, 10 Nov 2016 02:42:26 GMT  
		Size: 2.7 KB (2678 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4ddd4bc60abdbbd5bf35ab6b44b074cdbcfb33697e0700c1b9f16851513df96c`  
		Last Modified: Thu, 10 Nov 2016 02:42:26 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
