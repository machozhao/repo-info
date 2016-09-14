## `docker:git`

```console
$ docker pull docker@sha256:008e3e9811a718406b6f1453d306f192b9fb3f0f79e778a7c780052b96b28a9a
```

-	Platforms:
	-	linux; amd64

### `docker:git` - linux; amd64

-	Docker Version: 1.10.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **41.1 MB (41073197 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e23fe2a36144e98c94e90e839ec29613cd95db2280770d6337581fdfd4809e55`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["sh"]`

```dockerfile
# Thu, 23 Jun 2016 19:55:18 GMT
ADD file:852e9d0cb9d906535af512a89339fc70b2873a0f94defbcbe41cd44942dd6ac8 in /
# Thu, 23 Jun 2016 20:17:11 GMT
RUN apk add --no-cache 		ca-certificates 		curl 		openssl
# Thu, 23 Jun 2016 20:18:26 GMT
ENV DOCKER_BUCKET=get.docker.com
# Mon, 22 Aug 2016 19:10:44 GMT
ENV DOCKER_VERSION=1.12.1
# Mon, 22 Aug 2016 19:10:45 GMT
ENV DOCKER_SHA256=05ceec7fd937e1416e5dce12b0b6e1c655907d349d52574319a1e875077ccb79
# Mon, 22 Aug 2016 19:10:50 GMT
RUN set -x 	&& curl -fSL "https://${DOCKER_BUCKET}/builds/Linux/x86_64/docker-${DOCKER_VERSION}.tgz" -o docker.tgz 	&& echo "${DOCKER_SHA256} *docker.tgz" | sha256sum -c - 	&& tar -xzvf docker.tgz 	&& mv docker/* /usr/local/bin/ 	&& rmdir docker 	&& rm docker.tgz 	&& docker -v
# Mon, 22 Aug 2016 19:10:50 GMT
COPY file:50006c902e7677711aeffe4ab7b7042d649618b96dec760f322a8566dd83ab25 in /usr/local/bin/
# Mon, 22 Aug 2016 19:10:51 GMT
ENTRYPOINT &{["docker-entrypoint.sh"]}
# Mon, 22 Aug 2016 19:10:51 GMT
CMD ["sh"]
# Mon, 22 Aug 2016 19:11:08 GMT
RUN apk add --no-cache 		git 		openssh-client
```

-	Layers:
	-	`sha256:e110a4a1794126ef308a49f2d65785af2f25538f06700721aad8283b81fdfa58`  
		Last Modified: Thu, 23 Jun 2016 19:56:16 GMT  
		Size: 2.3 MB (2310286 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49e2842bdfdf9757b6fb042a914386833eb89594a0f6643fc8a7ca8e925dd58c`  
		Last Modified: Thu, 23 Jun 2016 20:17:29 GMT  
		Size: 913.0 KB (913008 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3a2cb1f9e6935a5b586ef30fc28e27fc1db84218d14c8a12d8e8bbd3be2ff16`  
		Last Modified: Mon, 22 Aug 2016 19:11:34 GMT  
		Size: 28.7 MB (28711003 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50ef1d41935ed603a4247d5437135bb6fabd59fc984d53789563f0aad49b9c77`  
		Last Modified: Mon, 22 Aug 2016 19:11:21 GMT  
		Size: 466.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:72c973df45af65df33bfb55db6f920e960fe3bb7507b4cdee1c87c6d5428c967`  
		Last Modified: Mon, 22 Aug 2016 19:13:39 GMT  
		Size: 9.1 MB (9138434 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip