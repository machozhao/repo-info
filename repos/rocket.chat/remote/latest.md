## `rocket.chat:latest`

```console
$ docker pull rocket.chat@sha256:a3ab7aaf11d3c8cf2645d072c340ffa25762d2eee2d97b7ef0c7cec394324665
```

-	Platforms:
	-	linux; amd64

### `rocket.chat:latest` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **195.9 MB (195927685 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:882239aa781a5dee8931bac490207656d110ccd410e08a46536d63a04a6c6480`
-	Default Command: `["node","main.js"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Mon, 07 Nov 2016 22:27:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 22:45:04 GMT
RUN groupadd -r node && useradd -r -g node node
# Tue, 08 Nov 2016 22:45:17 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     0034A06D9D9B0064CE8ADF6BF1747F4AD2306D93     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key";   done
# Tue, 08 Nov 2016 22:47:23 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Thu, 10 Nov 2016 02:21:40 GMT
ENV NODE_VERSION=4.6.2
# Thu, 10 Nov 2016 02:21:49 GMT
RUN buildDeps='xz-utils'     && set -x     && apt-get update && apt-get install -y $buildDeps --no-install-recommends     && rm -rf /var/lib/apt/lists/*     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION-linux-x64.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xJf "node-v$NODE_VERSION-linux-x64.tar.xz" -C /usr/local --strip-components=1     && rm "node-v$NODE_VERSION-linux-x64.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt     && apt-get purge -y --auto-remove $buildDeps     && ln -s /usr/local/bin/node /usr/local/bin/nodejs
# Thu, 10 Nov 2016 02:21:49 GMT
CMD ["node"]
# Thu, 10 Nov 2016 02:58:47 GMT
MAINTAINER buildmaster@rocket.chat
# Thu, 10 Nov 2016 02:58:47 GMT
RUN groupadd -r rocketchat &&  useradd -r -g rocketchat rocketchat
# Thu, 10 Nov 2016 02:58:48 GMT
VOLUME [/app/uploads]
# Thu, 10 Nov 2016 02:58:50 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 0E163286C20D07B9787EBE9FD7F9D0414FD08104
# Thu, 10 Nov 2016 02:58:50 GMT
ENV RC_VERSION=0.45.0
# Thu, 10 Nov 2016 02:58:51 GMT
WORKDIR /app
# Thu, 10 Nov 2016 02:59:27 GMT
RUN curl -fSL "https://rocket.chat/releases/${RC_VERSION}/download" -o rocket.chat.tgz &&  curl -fSL "https://rocket.chat/releases/${RC_VERSION}/asc" -o rocket.chat.tgz.asc &&  gpg --batch --verify rocket.chat.tgz.asc rocket.chat.tgz &&  tar zxvf rocket.chat.tgz &&  rm rocket.chat.tgz rocket.chat.tgz.asc &&  cd bundle/programs/server &&  npm install
# Thu, 10 Nov 2016 02:59:34 GMT
USER [rocketchat]
# Thu, 10 Nov 2016 02:59:35 GMT
WORKDIR /app/bundle
# Thu, 10 Nov 2016 02:59:35 GMT
ENV MONGO_URL=mongodb://db:27017/meteor HOME=/tmp PORT=3000 ROOT_URL=http://localhost:3000 Accounts_AvatarStorePath=/app/uploads
# Thu, 10 Nov 2016 02:59:36 GMT
EXPOSE 3000/tcp
# Thu, 10 Nov 2016 02:59:36 GMT
CMD ["node" "main.js"]
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
	-	`sha256:60721b40a88024b354485a2aab8916faa195b40c4fdba227e92f60c609f01156`  
		Last Modified: Tue, 08 Nov 2016 22:45:51 GMT  
		Size: 2.0 KB (2041 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3739ddf6315c5e18b3e9b8b61629bf3ce0a4f5c41e495a001023d86a46ef0d52`  
		Last Modified: Tue, 08 Nov 2016 22:45:52 GMT  
		Size: 97.2 KB (97211 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:635046ae112f09579446feb482ed56dab57c3099ef5f8287ed038b0d1ad9fdc5`  
		Last Modified: Thu, 10 Nov 2016 02:32:44 GMT  
		Size: 12.3 MB (12250713 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7761659d01e34c0a365bc8ba4047ad7390b1d4bf050aa32f29e3933d9e4caf9a`  
		Last Modified: Thu, 10 Nov 2016 02:59:47 GMT  
		Size: 2.1 KB (2088 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3e6784586e8374a6f2d28940119992b837d7753e937e3d5c6f9e706ff77dc85b`  
		Last Modified: Thu, 10 Nov 2016 02:59:48 GMT  
		Size: 94.7 KB (94663 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fcfd384af6297f904914b815899fd9268c0b8d7f2b22d540f0bd1200a5547251`  
		Last Modified: Thu, 10 Nov 2016 03:00:27 GMT  
		Size: 113.6 MB (113595503 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
