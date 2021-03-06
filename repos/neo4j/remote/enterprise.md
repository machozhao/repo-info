## `neo4j:enterprise`

```console
$ docker pull neo4j@sha256:81d5ac053396889d65a6adb8c765d46929db4b1c18ff5c6c919fe6cb537c2222
```

-	Platforms:
	-	linux; amd64

### `neo4j:enterprise` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **188.0 MB (188021030 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f258371245bfa11123c8988fc04e9eb120e1655fec80ea357c5ec523f6b0e7f2`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["neo4j"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Mon, 07 Nov 2016 22:27:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 18:52:12 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 18:53:53 GMT
RUN echo 'deb http://deb.debian.org/debian jessie-backports main' > /etc/apt/sources.list.d/jessie-backports.list
# Tue, 08 Nov 2016 18:53:53 GMT
ENV LANG=C.UTF-8
# Tue, 08 Nov 2016 18:53:54 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 08 Nov 2016 18:53:55 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre
# Tue, 08 Nov 2016 18:53:55 GMT
ENV JAVA_VERSION=8u111
# Tue, 08 Nov 2016 18:53:55 GMT
ENV JAVA_DEBIAN_VERSION=8u111-b14-2~bpo8+1
# Tue, 08 Nov 2016 18:53:56 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20140324
# Tue, 08 Nov 2016 18:54:18 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		openjdk-8-jre-headless="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	&& rm -rf /var/lib/apt/lists/* 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Tue, 08 Nov 2016 18:54:26 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Fri, 11 Nov 2016 19:17:45 GMT
ENV NEO4J_SHA256=92edf396616be8a1cdb41dd05c300865959f97944f4fe7f50539401a49c095d5
# Fri, 11 Nov 2016 19:17:45 GMT
ENV NEO4J_TARBALL=neo4j-enterprise-3.0.7-unix.tar.gz
# Fri, 11 Nov 2016 19:17:46 GMT
ARG NEO4J_URI=http://dist.neo4j.org/neo4j-enterprise-3.0.7-unix.tar.gz
# Fri, 11 Nov 2016 19:17:46 GMT
COPY file:2e411d607fa15f91ae6f4b515dde6bf3e158d34c0036556e00553ed1c50cd63d in /tmp/ 
# Fri, 11 Nov 2016 19:17:57 GMT
# ARGS: NEO4J_URI=http://dist.neo4j.org/neo4j-enterprise-3.0.7-unix.tar.gz
RUN curl --fail --silent --show-error --location --remote-name ${NEO4J_URI}     && echo "${NEO4J_SHA256} ${NEO4J_TARBALL}" | sha256sum --check --quiet -     && tar --extract --file ${NEO4J_TARBALL} --directory /var/lib     && mv /var/lib/neo4j-* /var/lib/neo4j     && rm ${NEO4J_TARBALL}
# Fri, 11 Nov 2016 19:17:57 GMT
WORKDIR /var/lib/neo4j
# Fri, 11 Nov 2016 19:17:58 GMT
# ARGS: NEO4J_URI=http://dist.neo4j.org/neo4j-enterprise-3.0.7-unix.tar.gz
RUN mv data /data     && ln --symbolic /data
# Fri, 11 Nov 2016 19:17:58 GMT
VOLUME [/data]
# Fri, 11 Nov 2016 19:17:59 GMT
COPY file:0944a2cbfb3872ef080e1d4d523c9d1bc7e6051f44ee5f024ab6840af5914b11 in /docker-entrypoint.sh 
# Fri, 11 Nov 2016 19:17:59 GMT
EXPOSE 7473/tcp 7474/tcp 7687/tcp
# Fri, 11 Nov 2016 19:18:00 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Fri, 11 Nov 2016 19:18:00 GMT
CMD ["neo4j"]
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
	-	`sha256:3e2e387eb26a1afa07fb24ab119e8680fc80f43a194890da1d1bb21f76e23c5e`  
		Last Modified: Tue, 08 Nov 2016 19:04:01 GMT  
		Size: 566.9 KB (566896 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eef540699244c02b2a8e14c3b4f335314506cb4b12e15c867535cb20ac429a37`  
		Last Modified: Tue, 08 Nov 2016 19:11:43 GMT  
		Size: 217.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1624a2f8d1142bb2aed22223df10c5416ff37b599ff48c724d23347d37b2b20e`  
		Last Modified: Tue, 08 Nov 2016 19:11:45 GMT  
		Size: 242.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7018f4ec6e0ab2d452cd6ac9600b8cfa25bcd10c603db8ad9107677e9f8fe15e`  
		Last Modified: Tue, 08 Nov 2016 19:12:03 GMT  
		Size: 53.5 MB (53450336 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6ca3bc2ad3b37551550f7c86d23f4e25066740db6d2f99c3ba99c0f9e0a4d3ec`  
		Last Modified: Tue, 08 Nov 2016 19:11:44 GMT  
		Size: 284.2 KB (284177 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:be8ac9c24ac5c3581f933f0893306fb7963c2f4a16b1b7eb84861c83c2d98337`  
		Last Modified: Fri, 11 Nov 2016 19:19:11 GMT  
		Size: 128.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b98eb6872a10de1e9cbcb9daafb38d8e88117a1d879acd055114c9d2b90e2520`  
		Last Modified: Fri, 11 Nov 2016 19:19:17 GMT  
		Size: 63.8 MB (63831948 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:43872bac315760c0ce189dff8345cb746f178321d16d3bf9a5b4a6ba7641af5c`  
		Last Modified: Fri, 11 Nov 2016 19:19:11 GMT  
		Size: 213.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:692f82bde3bb91243e425bdcf395b60f3537b559a65a934a1c63bd53b206ef7c`  
		Last Modified: Fri, 11 Nov 2016 19:19:10 GMT  
		Size: 1.4 KB (1407 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
