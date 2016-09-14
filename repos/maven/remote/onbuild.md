## `maven:onbuild`

```console
$ docker pull maven@sha256:237f0b9bb30f3303bfc3126dc1df83bad0083e981a345eb1e894a13c5f64cf16
```

-	Platforms:
	-	linux; amd64

### `maven:onbuild` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **251.9 MB (251941903 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0ee5900fafd08edb9fd1e5557265ec26a7c3692a50668900e3992b1d314b0c5a`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Tue, 30 Aug 2016 21:00:51 GMT
ADD file:f2453b914e7e026efd39c6321c7b14509b6d09dd3cf5567a8f6bd38466e06954 in / 
# Tue, 30 Aug 2016 21:00:52 GMT
CMD ["/bin/bash"]
# Tue, 30 Aug 2016 21:52:11 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 30 Aug 2016 21:52:34 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Wed, 31 Aug 2016 17:12:26 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 31 Aug 2016 17:15:01 GMT
RUN echo 'deb http://httpredir.debian.org/debian jessie-backports main' > /etc/apt/sources.list.d/jessie-backports.list
# Wed, 31 Aug 2016 17:15:01 GMT
ENV LANG=C.UTF-8
# Wed, 31 Aug 2016 17:15:02 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 31 Aug 2016 17:15:02 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
# Wed, 31 Aug 2016 17:15:02 GMT
ENV JAVA_VERSION=8u102
# Wed, 31 Aug 2016 17:15:03 GMT
ENV JAVA_DEBIAN_VERSION=8u102-b14.1-1~bpo8+1
# Wed, 31 Aug 2016 17:15:03 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20140324
# Wed, 31 Aug 2016 17:16:04 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		openjdk-8-jdk="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	&& rm -rf /var/lib/apt/lists/* 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 31 Aug 2016 17:16:05 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Wed, 31 Aug 2016 21:08:40 GMT
ARG MAVEN_VERSION=3.3.9
# Wed, 31 Aug 2016 21:08:40 GMT
ARG USER_HOME_DIR=/root
# Wed, 31 Aug 2016 21:08:41 GMT
# ARGS: MAVEN_VERSION=3.3.9 USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL http://apache.osuosl.org/maven/maven-3/$MAVEN_VERSION/binaries/apache-maven-$MAVEN_VERSION-bin.tar.gz     | tar -xzC /usr/share/maven --strip-components=1   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Wed, 31 Aug 2016 21:08:42 GMT
ENV MAVEN_HOME=/usr/share/maven
# Wed, 31 Aug 2016 21:08:42 GMT
ENV MAVEN_CONFIG=/root/.m2
# Wed, 31 Aug 2016 21:08:42 GMT
COPY file:e3aa30a24fcf60a59710465ac66fc1d53c35590a74fcdd51e12a5cbce393904b in /usr/local/bin/mvn-entrypoint.sh 
# Wed, 31 Aug 2016 21:08:43 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Wed, 31 Aug 2016 21:08:43 GMT
VOLUME [/root/.m2]
# Wed, 31 Aug 2016 21:08:43 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Wed, 31 Aug 2016 21:08:44 GMT
CMD ["mvn"]
# Wed, 31 Aug 2016 21:10:41 GMT
RUN mkdir -p /usr/src/app
# Wed, 31 Aug 2016 21:10:41 GMT
WORKDIR /usr/src/app
# Wed, 31 Aug 2016 21:10:42 GMT
ONBUILD ADD . /usr/src/app
# Wed, 31 Aug 2016 21:10:42 GMT
ONBUILD RUN mvn install
```

-	Layers:
	-	`sha256:8ad8b3f87b378cfae583fef34e47a3c9203847d779961b7351cbf786af0bc09f`  
		Last Modified: Tue, 30 Aug 2016 21:02:02 GMT  
		Size: 51.4 MB (51367268 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:751fe39c4d348c7fc411d46929c1dac390e3d7107efc9f8f69641b50e14459f7`  
		Last Modified: Tue, 30 Aug 2016 21:59:08 GMT  
		Size: 18.5 MB (18527264 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae3b77eefc06095198ecb7e758833493eab01708fae7f408b0631e6463c31a48`  
		Last Modified: Tue, 30 Aug 2016 21:59:22 GMT  
		Size: 42.5 MB (42495629 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8b357fc28db91a380d7af3e914aecbd0f395b8a84892ace50c54abb56460fe87`  
		Last Modified: Wed, 31 Aug 2016 17:21:39 GMT  
		Size: 593.3 KB (593342 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1a614fcb4b1be6e9b94f188ac859803e5214d24c2af86c6437bd74817e75613d`  
		Last Modified: Wed, 31 Aug 2016 17:26:12 GMT  
		Size: 218.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1fcd29499236d6a936fbacb8d65340eeb7177b930148fb1c401d5fa71ab88c82`  
		Last Modified: Wed, 31 Aug 2016 17:26:12 GMT  
		Size: 240.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1df99ed2f401ca635670635998c2b540cc748e390ffd8b47a2092815e6cb56b6`  
		Last Modified: Wed, 31 Aug 2016 17:26:53 GMT  
		Size: 130.1 MB (130073666 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c4b6cf75aef4eade93918ef73b6c2896c664f50fdb8e6f5e4c586c05a3d4c864`  
		Last Modified: Wed, 31 Aug 2016 17:26:13 GMT  
		Size: 284.2 KB (284227 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9530c9c753987e50d8b618d828ab559529c6d168decd110b00dc420d3f06f2f`  
		Last Modified: Wed, 31 Aug 2016 21:08:51 GMT  
		Size: 8.6 MB (8598847 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7b11c85df0f6231a6db532099b8b2140baf92d6c626130b08383bc8dbb3344ee`  
		Last Modified: Wed, 31 Aug 2016 21:08:50 GMT  
		Size: 691.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:738259c5fcae4e5a0292b0cce6035e868d5d2b52cb6149db23718b8219881cba`  
		Last Modified: Wed, 31 Aug 2016 21:08:49 GMT  
		Size: 350.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3c3a2801393898ff0075b7d7a4868cbc45230d628c53d2ddfd3cc40122e2f610`  
		Last Modified: Wed, 31 Aug 2016 21:10:47 GMT  
		Size: 161.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip