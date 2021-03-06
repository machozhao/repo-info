## `nginx:latest`

```console
$ docker pull nginx@sha256:9038d5645fa5fcca445d12e1b8979c87f46ca42cfb17beb1e5e093785991a639
```

-	Platforms:
	-	linux; amd64

### `nginx:latest` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **71.5 MB (71493599 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:05a60462f8bafb215ddc5c20a364b5fb637670200a74a5bb13a1b23f64515561`
-	Default Command: `["nginx","-g","daemon off;"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 22:40:20 GMT
MAINTAINER NGINX Docker Maintainers "docker-maint@nginx.com"
# Tue, 08 Nov 2016 22:40:28 GMT
ENV NGINX_VERSION=1.11.5-1~jessie
# Tue, 08 Nov 2016 22:40:54 GMT
RUN apt-key adv --keyserver hkp://pgp.mit.edu:80 --recv-keys 573BFD6B3D8FBC641079A6ABABF5BD827BD9BF62 	&& echo "deb http://nginx.org/packages/mainline/debian/ jessie nginx" >> /etc/apt/sources.list 	&& apt-get update 	&& apt-get install --no-install-recommends --no-install-suggests -y 						ca-certificates 						nginx=${NGINX_VERSION} 						nginx-module-xslt 						nginx-module-geoip 						nginx-module-image-filter 						nginx-module-perl 						nginx-module-njs 						gettext-base 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 22:41:00 GMT
RUN ln -sf /dev/stdout /var/log/nginx/access.log 	&& ln -sf /dev/stderr /var/log/nginx/error.log
# Tue, 08 Nov 2016 22:41:08 GMT
EXPOSE 443/tcp 80/tcp
# Tue, 08 Nov 2016 22:41:15 GMT
CMD ["nginx" "-g" "daemon off;"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7bdb4b002d7f7d49c950892ced43ca0c3ee7a7f61949435d01811478791aa651`  
		Last Modified: Tue, 08 Nov 2016 22:41:42 GMT  
		Size: 20.1 MB (20136414 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49b006ddea702f71c6c6b393a663dc9b1d2db7fc3451b2c6f28251c170d57208`  
		Last Modified: Tue, 08 Nov 2016 22:41:35 GMT  
		Size: 196.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
