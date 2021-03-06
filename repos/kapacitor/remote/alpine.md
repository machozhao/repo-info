## `kapacitor:alpine`

```console
$ docker pull kapacitor@sha256:8a8f94641f5df22a3d33c331bd09fb53a0ec161105ca7d6bcc8be3cd29ae1ccc
```

-	Platforms:
	-	linux; amd64

### `kapacitor:alpine` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **8.9 MB (8937224 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:59be1f2192711a782853802614593078c7afbd960119291b5027c484523b5fdf`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["kapacitord"]`

```dockerfile
# Tue, 18 Oct 2016 20:31:22 GMT
ADD file:7afbc23fda8b0b3872623c16af8e3490b2cee951aed14b3794389c2f946cc8c7 in / 
# Tue, 08 Nov 2016 22:31:36 GMT
ENV KAPACITOR_VERSION=1.1.0
# Tue, 08 Nov 2016 22:31:45 GMT
RUN apk add --no-cache --virtual .build-deps wget gnupg tar ca-certificates &&     update-ca-certificates &&     gpg --keyserver hkp://ha.pool.sks-keyservers.net         --recv-keys 05CE15085FC09D18E99EFB22684A14CF2582E0C5 &&     wget -q https://dl.influxdata.com/kapacitor/releases/kapacitor-${KAPACITOR_VERSION}-static_linux_amd64.tar.gz.asc &&     wget -q https://dl.influxdata.com/kapacitor/releases/kapacitor-${KAPACITOR_VERSION}-static_linux_amd64.tar.gz &&     gpg --batch --verify kapacitor-${KAPACITOR_VERSION}-static_linux_amd64.tar.gz.asc kapacitor-${KAPACITOR_VERSION}-static_linux_amd64.tar.gz &&     mkdir -p /usr/src &&     tar -C /usr/src -xzf kapacitor-${KAPACITOR_VERSION}-static_linux_amd64.tar.gz &&     rm -f /usr/src/kapacitor-*/kapacitor.conf &&     chmod +x /usr/src/kapacitor-*/* &&     cp -a /usr/src/kapacitor-*/* /usr/bin/ &&     rm -rf *.tar.gz* /usr/src /root/.gnupg &&     apk del .build-deps
# Tue, 08 Nov 2016 22:31:46 GMT
COPY file:965f70a8f6603417e3e4564d3c3f35b5941a4ba7cb09a86047810948e33d0831 in /etc/kapacitor/kapacitor.conf 
# Tue, 08 Nov 2016 22:31:46 GMT
EXPOSE 9092/tcp
# Tue, 08 Nov 2016 22:31:47 GMT
VOLUME [/var/lib/kapacitor]
# Tue, 08 Nov 2016 22:31:47 GMT
COPY file:440a837280df72a19ed72b91fab9bdcfd268250b241bbc22509699f880fe0d17 in /entrypoint.sh 
# Tue, 08 Nov 2016 22:31:48 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Tue, 08 Nov 2016 22:31:48 GMT
CMD ["kapacitord"]
```

-	Layers:
	-	`sha256:3690ec4760f95690944da86dc4496148a63d85c9e3100669a318110092f6862f`  
		Last Modified: Tue, 18 Oct 2016 20:32:39 GMT  
		Size: 2.3 MB (2312958 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c7615874591fcf067a05bff2c90a4770723d6ddc9c4288961f8f987d1ff2a9d3`  
		Last Modified: Tue, 08 Nov 2016 22:33:52 GMT  
		Size: 6.6 MB (6623822 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:43c97bf8829b25f6f10973578946d29a768662badde6d3c8c35871736fa46dc8`  
		Last Modified: Tue, 08 Nov 2016 22:33:48 GMT  
		Size: 218.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:164bd7f99ebdae828abae189f9c5c0f89259da133df561082ec0c263d807ef3d`  
		Last Modified: Tue, 08 Nov 2016 22:33:48 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
