## `maven:3-jdk-9`

```console
$ docker pull maven@sha256:71ad8904bcd321501b885eee9873ffc236797c4a0d4c563ec54f68eec6ab3916
```

-	Platforms:
	-	linux; amd64

### `maven:3-jdk-9` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **247.9 MB (247934307 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0574cbe67e771bb099b901fda701ffc439056d6aa7a023879c7c264c157f8185`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Tue, 30 Aug 2016 21:01:05 GMT
ADD file:cde9313f179951bdf9a85569736d1720e757e4b3710e422228ba66a1789469a9 in / 
# Tue, 30 Aug 2016 21:01:05 GMT
CMD ["/bin/bash"]
# Tue, 30 Aug 2016 21:53:56 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 30 Aug 2016 21:54:11 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Wed, 31 Aug 2016 17:16:55 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 31 Aug 2016 17:16:56 GMT
RUN echo 'deb http://httpredir.debian.org/debian experimental main' > /etc/apt/sources.list.d/experimental.list
# Wed, 31 Aug 2016 17:16:56 GMT
ENV LANG=C.UTF-8
# Wed, 31 Aug 2016 17:16:57 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 31 Aug 2016 17:16:57 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-9-openjdk-amd64
# Wed, 07 Sep 2016 18:07:55 GMT
ENV JAVA_VERSION=9~b134
# Wed, 07 Sep 2016 18:07:55 GMT
ENV JAVA_DEBIAN_VERSION=9~b134-2
# Wed, 07 Sep 2016 18:08:28 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		openjdk-9-jdk-headless="$JAVA_DEBIAN_VERSION" 	&& rm -rf /var/lib/apt/lists/* 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 07 Sep 2016 21:35:48 GMT
ARG MAVEN_VERSION=3.3.9
# Wed, 07 Sep 2016 21:35:49 GMT
ARG USER_HOME_DIR=/root
# Wed, 07 Sep 2016 21:35:51 GMT
# ARGS: MAVEN_VERSION=3.3.9 USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL http://apache.osuosl.org/maven/maven-3/$MAVEN_VERSION/binaries/apache-maven-$MAVEN_VERSION-bin.tar.gz     | tar -xzC /usr/share/maven --strip-components=1   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Wed, 07 Sep 2016 21:35:52 GMT
ENV MAVEN_HOME=/usr/share/maven
# Wed, 07 Sep 2016 21:35:52 GMT
ENV MAVEN_CONFIG=/root/.m2
# Wed, 07 Sep 2016 21:35:52 GMT
COPY file:e3aa30a24fcf60a59710465ac66fc1d53c35590a74fcdd51e12a5cbce393904b in /usr/local/bin/mvn-entrypoint.sh 
# Wed, 07 Sep 2016 21:35:53 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Wed, 07 Sep 2016 21:35:53 GMT
VOLUME [/root/.m2]
# Wed, 07 Sep 2016 21:35:53 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Wed, 07 Sep 2016 21:35:54 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:f45860c16bdb654da5c2c7bea335dcb2db33cf95ace30c719175aef1a0d41fbb`  
		Last Modified: Tue, 30 Aug 2016 21:03:28 GMT  
		Size: 42.5 MB (42455191 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:af28bbafd0e3620fa7da5fba49de724bc4c40d71bee92937c0e52f24d3e1eb9b`  
		Last Modified: Tue, 30 Aug 2016 22:01:19 GMT  
		Size: 20.5 MB (20547306 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:469d6b6129b0efb9c583749806287b09e55305db0d5a394bebf242b9be3b0d13`  
		Last Modified: Tue, 30 Aug 2016 22:01:37 GMT  
		Size: 48.1 MB (48089667 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:31e9a7208ad8b35f80cc0dbc210327b873d2d3e316f8ef1e65cad78759aac631`  
		Last Modified: Wed, 31 Aug 2016 17:31:37 GMT  
		Size: 592.0 KB (591960 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:89b155245e34ebe588c54045dfac4190425d1f8680b38f90341a086d86308b8f`  
		Last Modified: Wed, 31 Aug 2016 17:31:35 GMT  
		Size: 218.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5ce7db45669479028025bf0f725a7ef6ae754d637f9d5fa68fa5bb1073ce7d8d`  
		Last Modified: Wed, 31 Aug 2016 17:31:35 GMT  
		Size: 242.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:914b3ea7d9fdb6f8df63715e00426d6036c7086bd4ae6c42c197bdbc17681a79`  
		Last Modified: Wed, 07 Sep 2016 18:16:52 GMT  
		Size: 127.6 MB (127649835 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:134ff418067cfc4c5056da922226a39c871ad2793b88792488dfd9d25c598807`  
		Last Modified: Wed, 07 Sep 2016 21:36:00 GMT  
		Size: 8.6 MB (8598850 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9a0b31e69bf915dfb4439d7fdd21610b154ef7df6cd389c891c88540f54e1aae`  
		Last Modified: Wed, 07 Sep 2016 21:35:59 GMT  
		Size: 691.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fbb7ea9a2c9d37319d3531e23a5e6e425edc15438191a0016bbc3373eb91d35a`  
		Last Modified: Wed, 07 Sep 2016 21:36:00 GMT  
		Size: 347.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip