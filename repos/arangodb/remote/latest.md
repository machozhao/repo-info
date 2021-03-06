## `arangodb:latest`

```console
$ docker pull arangodb@sha256:b6c7a1f0163ea155456910e4b64053255b827ecefbc339ad3b1027077d081954
```

-	Platforms:
	-	linux; amd64

### `arangodb:latest` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **119.1 MB (119126930 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7697f3e45ffb9ac5ef24afca2b24114234d9ba56b5e54a747dfce0375d298762`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["arangod"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 18:42:33 GMT
MAINTAINER Frank Celler <info@arangodb.com>
# Tue, 08 Nov 2016 18:49:29 GMT
ENV ARCHITECTURE=amd64
# Tue, 08 Nov 2016 18:49:29 GMT
ENV ARANGO_VERSION=3.0.10
# Tue, 08 Nov 2016 18:49:29 GMT
ENV ARANGO_URL=https://www.arangodb.com/repositories/arangodb3/Debian_8.0
# Tue, 08 Nov 2016 18:49:30 GMT
ENV ARANGO_PACKAGE=arangodb3_3.0.10_amd64.deb
# Tue, 08 Nov 2016 18:49:30 GMT
ENV ARANGO_PACKAGE_URL=https://www.arangodb.com/repositories/arangodb3/Debian_8.0/amd64/arangodb3_3.0.10_amd64.deb
# Tue, 08 Nov 2016 18:49:30 GMT
ENV ARANGO_SIGNATURE_URL=https://www.arangodb.com/repositories/arangodb3/Debian_8.0/amd64/arangodb3_3.0.10_amd64.deb.asc
# Tue, 08 Nov 2016 18:49:32 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys CD8CB0F1E0AD5B52E93F41E7EA93F5E56E751E9B
# Tue, 08 Nov 2016 18:49:43 GMT
RUN apt-get update &&     apt-get install -y --no-install-recommends         libjemalloc1 	libsnappy1         ca-certificates         pwgen         curl     &&     rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 18:49:44 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 08 Nov 2016 18:50:13 GMT
RUN curl -O ${ARANGO_SIGNATURE_URL} &&           curl -O ${ARANGO_PACKAGE_URL} &&             gpg --verify ${ARANGO_PACKAGE}.asc &&     (echo arangodb3 arangodb3/password password test | debconf-set-selections) &&     (echo arangodb3 arangodb3/password_again password test | debconf-set-selections) &&     DEBIAN_FRONTEND="noninteractive" dpkg -i ${ARANGO_PACKAGE} &&     rm -rf /var/lib/arangodb3/* &&     sed -ri         -e 's!127\.0\.0\.1!0.0.0.0!g'         -e 's!^(file\s*=).*!\1 -!'         -e 's!^#\s*uid\s*=.*!uid = arangodb!'         -e 's!^#\s*gid\s*=.*!gid = arangodb!'         /etc/arangodb3/arangod.conf     &&     DEBIAN_FRONTEND="noninteractive" apt-get purge -y --auto-remove ca-certificates &&     rm -f ${ARANGO_PACKAGE}*
# Tue, 08 Nov 2016 18:50:14 GMT
VOLUME [/var/lib/arangodb3 /var/lib/arangodb3-apps]
# Tue, 08 Nov 2016 18:50:16 GMT
COPY file:b4d76a688137b83503d77bb818e5dfa72d9e1f7b1e660f6d81e5a2ad5567e562 in /entrypoint.sh 
# Tue, 08 Nov 2016 18:50:16 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Tue, 08 Nov 2016 18:50:16 GMT
EXPOSE 8529/tcp
# Tue, 08 Nov 2016 18:50:17 GMT
CMD ["arangod"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1ac6d3da111d1b2f69fa22d867e1c349cced152cd8648ef54b6774a9ad6fb6a3`  
		Last Modified: Tue, 08 Nov 2016 18:50:29 GMT  
		Size: 7.4 KB (7367 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae0ff0549304b179885dd00b753fa64b6a85c946117a68e79329ca0ca53a80f7`  
		Last Modified: Tue, 08 Nov 2016 18:50:31 GMT  
		Size: 6.7 MB (6683864 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0e71666cba7ee17069301588ec7b99b54efed8c7caf4166135aba39ab1b6411`  
		Last Modified: Tue, 08 Nov 2016 18:50:29 GMT  
		Size: 113.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f587beba84c313b7f4480d3291b601386a49d0a5bd079b15d7be3934443269a`  
		Last Modified: Tue, 08 Nov 2016 18:50:51 GMT  
		Size: 61.1 MB (61077175 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9215eda1dae25bc9ec095994c1debcebcb48b26347eb26ba4e9f89b660e3ce20`  
		Last Modified: Tue, 08 Nov 2016 18:50:29 GMT  
		Size: 1.4 KB (1422 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
