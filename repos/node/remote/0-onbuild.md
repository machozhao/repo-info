## `node:0-onbuild`

```console
$ docker pull node@sha256:1392e9b67f85b2d5c48dd22c09f3866d0b3c606c728519334646f8ae90860678
```

-	Platforms:
	-	linux; amd64

### `node:0-onbuild` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **252.4 MB (252379537 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:cf88958a14ec995d88f1338945d2085a057af7f93a460bca34f22178ef47cc63`
-	Default Command: `["npm","start"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Mon, 07 Nov 2016 22:27:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Mon, 07 Nov 2016 22:27:51 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Mon, 07 Nov 2016 22:28:43 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		autoconf 		automake 		bzip2 		file 		g++ 		gcc 		imagemagick 		libbz2-dev 		libc6-dev 		libcurl4-openssl-dev 		libdb-dev 		libevent-dev 		libffi-dev 		libgdbm-dev 		libgeoip-dev 		libglib2.0-dev 		libjpeg-dev 		libkrb5-dev 		liblzma-dev 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libncurses-dev 		libpng-dev 		libpq-dev 		libreadline-dev 		libsqlite3-dev 		libssl-dev 		libtool 		libwebp-dev 		libxml2-dev 		libxslt-dev 		libyaml-dev 		make 		patch 		xz-utils 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Thu, 10 Nov 2016 02:19:38 GMT
RUN groupadd -r node && useradd -r -g node node
# Thu, 10 Nov 2016 02:20:43 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     0034A06D9D9B0064CE8ADF6BF1747F4AD2306D93     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key";   done
# Thu, 10 Nov 2016 02:21:55 GMT
ENV NODE_VERSION=0.12.17
# Thu, 10 Nov 2016 02:21:58 GMT
RUN curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz"   && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"   && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc   && grep " node-v$NODE_VERSION-linux-x64.tar.xz\$" SHASUMS256.txt | sha256sum -c -   && tar -xJf "node-v$NODE_VERSION-linux-x64.tar.xz" -C /usr/local --strip-components=1   && rm "node-v$NODE_VERSION-linux-x64.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt   && ln -s /usr/local/bin/node /usr/local/bin/nodejs
# Thu, 10 Nov 2016 02:21:59 GMT
CMD ["node"]
# Thu, 10 Nov 2016 02:22:00 GMT
RUN mkdir -p /usr/src/app
# Thu, 10 Nov 2016 02:22:00 GMT
WORKDIR /usr/src/app
# Thu, 10 Nov 2016 02:22:00 GMT
ONBUILD ARG NODE_ENV
# Thu, 10 Nov 2016 02:22:01 GMT
ONBUILD ENV NODE_ENV $NODE_ENV
# Thu, 10 Nov 2016 02:22:01 GMT
ONBUILD COPY package.json /usr/src/app/
# Thu, 10 Nov 2016 02:22:01 GMT
ONBUILD RUN npm install
# Thu, 10 Nov 2016 02:22:01 GMT
ONBUILD COPY . /usr/src/app
# Thu, 10 Nov 2016 02:22:02 GMT
CMD ["npm" "start"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:75ea8418708338e40dce9179cfe97fd116831f1601be50fef48ea6011653c986`  
		Last Modified: Mon, 07 Nov 2016 22:57:05 GMT  
		Size: 18.5 MB (18528477 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:88b459c9f665cc39ff5fc09071b5dada4dad766573d962276f999d0c466d5405`  
		Last Modified: Mon, 07 Nov 2016 22:57:53 GMT  
		Size: 42.5 MB (42498243 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1e3ee139a57774dc3728a4bf9675bc379458093585e42f384852e644b1b272ac`  
		Last Modified: Mon, 07 Nov 2016 22:59:05 GMT  
		Size: 129.8 MB (129808774 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bd2400e7d880dc68db3c01d136b8ee8ed6e846bbc2c97ac0655597a0b11b573a`  
		Last Modified: Thu, 10 Nov 2016 02:22:32 GMT  
		Size: 2.1 KB (2056 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b8c6812ba46984862fae512c3d1de8299a6819c8159fe022808ec254dc995cc6`  
		Last Modified: Thu, 10 Nov 2016 02:22:34 GMT  
		Size: 97.2 KB (97210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c3776f341f47305ecb648c377910e01590a44b8e29dc56cbf1fd095377e4f608`  
		Last Modified: Thu, 10 Nov 2016 02:35:09 GMT  
		Size: 10.1 MB (10087662 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9db724dde4b137f2f25cbed0a19f03a21297811e30fc92af93818bedb4c32f33`  
		Last Modified: Thu, 10 Nov 2016 02:36:06 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
