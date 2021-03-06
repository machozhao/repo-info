## `maven:3-jdk-7-onbuild-alpine`

```console
$ docker pull maven@sha256:64d7bae17c74b6d088db30ce66c45164e35f0113f93be40757d0379aaa07b4b1
```

-	Platforms:
	-	linux; amd64

### `maven:3-jdk-7-onbuild-alpine` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **88.2 MB (88193678 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a40f03731dd99c6c6b166af94f4113b423d34f4168ce62315c65d6340ad3adfc`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Tue, 18 Oct 2016 20:31:22 GMT
ADD file:7afbc23fda8b0b3872623c16af8e3490b2cee951aed14b3794389c2f946cc8c7 in / 
# Tue, 18 Oct 2016 20:39:57 GMT
ENV LANG=C.UTF-8
# Tue, 18 Oct 2016 20:39:58 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 18 Oct 2016 20:39:59 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.7-openjdk
# Tue, 18 Oct 2016 20:39:59 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.7-openjdk/jre/bin:/usr/lib/jvm/java-1.7-openjdk/bin
# Wed, 19 Oct 2016 22:02:07 GMT
ENV JAVA_VERSION=7u111
# Wed, 19 Oct 2016 22:02:07 GMT
ENV JAVA_ALPINE_VERSION=7.111.2.6.7-r2
# Wed, 19 Oct 2016 22:02:17 GMT
RUN set -x 	&& apk add --no-cache 		openjdk7="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Thu, 20 Oct 2016 00:55:24 GMT
RUN apk add --no-cache curl tar bash
# Thu, 20 Oct 2016 00:55:24 GMT
ARG MAVEN_VERSION=3.3.9
# Thu, 20 Oct 2016 00:55:25 GMT
ARG USER_HOME_DIR=/root
# Thu, 20 Oct 2016 00:55:26 GMT
# ARGS: MAVEN_VERSION=3.3.9 USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL http://apache.osuosl.org/maven/maven-3/$MAVEN_VERSION/binaries/apache-maven-$MAVEN_VERSION-bin.tar.gz     | tar -xzC /usr/share/maven --strip-components=1   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Thu, 20 Oct 2016 00:55:26 GMT
ENV MAVEN_HOME=/usr/share/maven
# Thu, 20 Oct 2016 00:55:27 GMT
ENV MAVEN_CONFIG=/root/.m2
# Thu, 20 Oct 2016 00:55:27 GMT
COPY file:e3aa30a24fcf60a59710465ac66fc1d53c35590a74fcdd51e12a5cbce393904b in /usr/local/bin/mvn-entrypoint.sh 
# Thu, 20 Oct 2016 00:55:28 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Thu, 20 Oct 2016 00:55:28 GMT
VOLUME [/root/.m2]
# Thu, 20 Oct 2016 00:55:29 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Thu, 20 Oct 2016 00:55:29 GMT
CMD ["mvn"]
# Thu, 20 Oct 2016 00:56:40 GMT
RUN mkdir -p /usr/src/app
# Thu, 20 Oct 2016 00:56:41 GMT
WORKDIR /usr/src/app
# Thu, 20 Oct 2016 00:56:41 GMT
ONBUILD ADD . /usr/src/app
# Thu, 20 Oct 2016 00:56:41 GMT
ONBUILD RUN mvn install
```

-	Layers:
	-	`sha256:3690ec4760f95690944da86dc4496148a63d85c9e3100669a318110092f6862f`  
		Last Modified: Tue, 18 Oct 2016 20:32:39 GMT  
		Size: 2.3 MB (2312958 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cfdb77eb56b4c44907a822ccdf607323c1f42fd024b7db6be146dd049d95f305`  
		Last Modified: Tue, 18 Oct 2016 20:45:34 GMT  
		Size: 230.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5e87eeb13ad9ed22981f9c0b7753f79568a84073d032ad7ac2310f0b494bfa1a`  
		Last Modified: Wed, 19 Oct 2016 22:06:24 GMT  
		Size: 75.5 MB (75549480 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:732c0fe2ddbc61e0483324efd0d4de1618742bc31745ae7bcd198c53ebe80b3e`  
		Last Modified: Thu, 20 Oct 2016 00:55:40 GMT  
		Size: 1.7 MB (1730974 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4c554515083d008a13d6a788009632fea3861de2a0a3fd506e28e5465ad8c910`  
		Last Modified: Thu, 20 Oct 2016 00:55:40 GMT  
		Size: 8.6 MB (8598845 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:517c1119d772706ad7049b420e73bae6a0b249bdb5d08d55f58f979fb5b80b90`  
		Last Modified: Thu, 20 Oct 2016 00:55:38 GMT  
		Size: 686.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c415d1171cba9e5ddfa7e2905d47d597d49b7145f638d45ddefd8905ea601dc3`  
		Last Modified: Thu, 20 Oct 2016 00:55:39 GMT  
		Size: 348.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7d11c7260eb5dd976e238636215cd86dd597c02b62e1a0b7b7721751da647db4`  
		Last Modified: Thu, 20 Oct 2016 00:56:51 GMT  
		Size: 157.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
