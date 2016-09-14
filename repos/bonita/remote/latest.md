## `bonita:latest`

```console
$ docker pull bonita@sha256:8931f0e0e4cc1cf5329f5a50845acd97d678fb13ddc505e4501feb3a0096c859
```

-	Platforms:
	-	linux; amd64

### `bonita:latest` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **216.5 MB (216460859 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:1824f12069b09e719ec52cbe82878cb992d718edc4157ae00ce43c964318cd62`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Tue, 30 Aug 2016 17:47:58 GMT
ADD file:ada91758a31d8de3c78ea0065fbc866430a71eb58bf5c4cb403d47052b1cade0 in / 
# Tue, 30 Aug 2016 17:47:59 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Tue, 30 Aug 2016 17:48:00 GMT
RUN rm -rf /var/lib/apt/lists/*
# Tue, 30 Aug 2016 17:48:00 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Tue, 30 Aug 2016 17:48:01 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Tue, 30 Aug 2016 17:48:01 GMT
CMD ["/bin/bash"]
# Tue, 30 Aug 2016 17:59:46 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Tue, 30 Aug 2016 18:00:23 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.5   openjdk-7-jre-headless   postgresql-client   unzip   wget   zip   && rm -rf /var/lib/apt/lists/*
# Tue, 30 Aug 2016 18:00:24 GMT
RUN mkdir /opt/custom-init.d/
# Tue, 30 Aug 2016 18:00:25 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Tue, 30 Aug 2016 18:00:27 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Tue, 30 Aug 2016 18:00:31 GMT
RUN wget -q "https://github.com/tianon/gosu/releases/download/1.6/gosu-$(dpkg --print-architecture)" -O /usr/local/bin/gosu   && wget -q "https://github.com/tianon/gosu/releases/download/1.6/gosu-$(dpkg --print-architecture).asc" -O /usr/local/bin/gosu.asc   && gpg --verify /usr/local/bin/gosu.asc   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Tue, 06 Sep 2016 19:53:03 GMT
ENV BONITA_VERSION=7.3.2
# Tue, 06 Sep 2016 19:53:03 GMT
ENV TOMCAT_VERSION=7.0.67
# Tue, 06 Sep 2016 19:53:04 GMT
ENV BONITA_SHA256=d021aaf96f50655e679526a9e8d77aa84fd159ff285cf2c280863c8b3fb88e40
# Tue, 06 Sep 2016 19:53:04 GMT
ENV POSTGRES_JDBC_DRIVER=postgresql-9.3-1102.jdbc41.jar
# Tue, 06 Sep 2016 19:53:04 GMT
ENV POSTGRES_SHA256=b78749d536da75c382d0a71c717cde6850df64e16594676fc7cacb5a74541d66
# Tue, 06 Sep 2016 19:53:04 GMT
ENV MYSQL_JDBC_DRIVER=mysql-connector-java-5.1.26
# Tue, 06 Sep 2016 19:53:05 GMT
ENV MYSQL_SHA256=40b2d49f6f2551cc7fa54552af806e8026bf8405f03342205852e57a3205a868
# Tue, 06 Sep 2016 19:53:08 GMT
RUN mkdir /opt/files   && wget -q https://jdbc.postgresql.org/download/${POSTGRES_JDBC_DRIVER} -O /opt/files/${POSTGRES_JDBC_DRIVER}   && echo "$POSTGRES_SHA256" /opt/files/${POSTGRES_JDBC_DRIVER} | sha256sum -c -   && wget -q http://dev.mysql.com/get/Downloads/Connector-J/${MYSQL_JDBC_DRIVER}.zip -O /opt/files/${MYSQL_JDBC_DRIVER}.zip   && echo "$MYSQL_SHA256" /opt/files/${MYSQL_JDBC_DRIVER}.zip | sha256sum -c -   && unzip -q /opt/files/${MYSQL_JDBC_DRIVER}.zip -d /opt/files/   && mv /opt/files/${MYSQL_JDBC_DRIVER}/${MYSQL_JDBC_DRIVER}-bin.jar /opt/files/   && rm -r /opt/files/${MYSQL_JDBC_DRIVER}   && rm /opt/files/${MYSQL_JDBC_DRIVER}.zip
# Tue, 06 Sep 2016 19:53:23 GMT
RUN wget -q http://download.forge.ow2.org/bonita/BonitaBPMCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip -O /opt/files/BonitaBPMCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip   && echo "$BONITA_SHA256" /opt/files/BonitaBPMCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Tue, 06 Sep 2016 19:53:23 GMT
VOLUME [/opt/bonita]
# Tue, 06 Sep 2016 19:53:24 GMT
COPY dir:fde4873241031c6b90b44319c923aea3900e89716d18d78efb0f8fd43ac375a6 in /opt/files 
# Tue, 06 Sep 2016 19:53:24 GMT
COPY dir:02b08d3b2ed19a654c43e135e71e47c809262f2a015647ff3da638716f22696f in /opt/templates 
# Tue, 06 Sep 2016 19:53:24 GMT
EXPOSE 8080/tcp
# Tue, 06 Sep 2016 19:53:25 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:862a3e9af0aeffe79345b790bad31baaa61e9402b6e616bff17babed6b053b54`  
		Last Modified: Fri, 26 Aug 2016 18:53:56 GMT  
		Size: 65.7 MB (65700923 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d0623aaf4140d62e6096882bf6762ea6b4baeea37eb933471f87a67fdff142b3`  
		Last Modified: Tue, 30 Aug 2016 23:30:35 GMT  
		Size: 71.6 KB (71565 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9274a13e26ac0f1c49ec236e6a74098e54f9622a12636f6dac9ba6b5dac33b2a`  
		Last Modified: Tue, 30 Aug 2016 23:30:35 GMT  
		Size: 359.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab185c837bea98a42b032bdf4621b6d8eb9ee617d1405f4110f38865ffc334e2`  
		Last Modified: Tue, 30 Aug 2016 23:30:34 GMT  
		Size: 681.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:55122420e5f51a86b316465bd5217ffc5a49292282b6d409753682c526cd82ff`  
		Last Modified: Tue, 30 Aug 2016 23:30:32 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f32e27f042ebf9dd2f70b589ecd24fe7f582ee4bc29b244786b2c5bb14d5272d`  
		Last Modified: Tue, 06 Sep 2016 19:53:50 GMT  
		Size: 65.0 MB (64972178 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:092ca0685a168043c010a92345c55c14fd447f907add5686f3bb5170d519e7f1`  
		Last Modified: Tue, 06 Sep 2016 19:53:35 GMT  
		Size: 119.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:98bbfbf8d1c0cb427022e80c8ff8e6ce1156b64041515cc2f265213d945ec38d`  
		Last Modified: Tue, 06 Sep 2016 19:53:34 GMT  
		Size: 1.8 KB (1786 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:16dab50676e0c88a2a0ad303226bf88cde793f8bfe263ee64491692aa0d2ba2d`  
		Last Modified: Tue, 06 Sep 2016 19:53:33 GMT  
		Size: 123.2 KB (123205 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:37aa2c2864dec899d2e221ae470c3f26521a7598d59dfe3a9e3fd7fd49c4b7a7`  
		Last Modified: Tue, 06 Sep 2016 19:53:32 GMT  
		Size: 807.6 KB (807588 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:385a4ce21f0dddfa5c7ead889f37cff119dc4d84c01bb3901f4960d49b6e6502`  
		Last Modified: Tue, 06 Sep 2016 19:54:05 GMT  
		Size: 1.4 MB (1382492 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bf9bf7521e981546878f321ea80f6967a8fbf7daf99d78597f295f0a405a403b`  
		Last Modified: Tue, 06 Sep 2016 19:54:11 GMT  
		Size: 83.4 MB (83390740 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a7e305cafef048777d91fe9bb023fa70e5cc4b93b6c199c5c93974160fe8ec68`  
		Last Modified: Tue, 06 Sep 2016 19:54:03 GMT  
		Size: 5.8 KB (5805 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:85469144f1e50a5e70c7add940069efa998202b8fd73dc8341ef1777a86dc02b`  
		Last Modified: Tue, 06 Sep 2016 19:54:03 GMT  
		Size: 3.3 KB (3255 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip