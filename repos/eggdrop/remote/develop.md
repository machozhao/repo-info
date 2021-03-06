## `eggdrop:develop`

```console
$ docker pull eggdrop@sha256:2cb5f114c9dd59a80699e7b498348f007042d9fe2d7b10ed980a3da5cec2842f
```

-	Platforms:
	-	linux; amd64

### `eggdrop:develop` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **8.3 MB (8283009 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c37c47a15e658e746ff201a9dce40a021dbd7066702eceab5b28344790e66d28`
-	Entrypoint: `["\/home\/eggdrop\/eggdrop\/entrypoint.sh"]`
-	Default Command: `["eggdrop.conf"]`

```dockerfile
# Tue, 18 Oct 2016 20:31:22 GMT
ADD file:7afbc23fda8b0b3872623c16af8e3490b2cee951aed14b3794389c2f946cc8c7 in / 
# Tue, 18 Oct 2016 23:12:44 GMT
MAINTAINER Geo Van O <geo@eggheads.org>
# Tue, 18 Oct 2016 23:12:45 GMT
RUN adduser -S eggdrop
# Tue, 18 Oct 2016 23:12:46 GMT
RUN apk add --no-cache 'su-exec>=0.2'
# Thu, 03 Nov 2016 16:38:14 GMT
ENV EGGDROP_SHA256=3edeb6aa4f8ba07502090ec8e20cd65eef6c57aa9038c62754b47eb84da2e8aa
# Thu, 03 Nov 2016 16:38:14 GMT
ENV EGGDROP_COMMIT=d4690467959e16c8c3f214233b75fa9afaf0490a
# Thu, 03 Nov 2016 16:38:52 GMT
RUN apk add --no-cache tcl tcl-dev wget ca-certificates make tar gpgme bash build-base   && wget https://github.com/eggheads/eggdrop/archive/$EGGDROP_COMMIT.tar.gz -O develop.tar.gz  && echo "$EGGDROP_SHA256  develop.tar.gz" | sha256sum -c -   && tar -zxvf develop.tar.gz   && rm develop.tar.gz     && ( cd eggdrop-$EGGDROP_COMMIT     && ./configure --with-tclinc=/usr/include/tcl8.6/tcl.h --with-tcllib=/usr/lib/x86_64-linux-gnu/libtcl8.6.so     && make config     && make     && make install DEST=/home/eggdrop/eggdrop )   && rm -rf eggdrop-$EGGDROP_COMMIT   && mkdir /home/eggdrop/eggdrop/data   && chown -R eggdrop /home/eggdrop/eggdrop   && apk del tcl-dev wget ca-certificates make tar gpgme build-base
# Thu, 03 Nov 2016 16:38:52 GMT
ENV NICK=
# Thu, 03 Nov 2016 16:38:52 GMT
ENV SERVER=
# Thu, 03 Nov 2016 16:38:53 GMT
ENV LISTEN=3333
# Thu, 03 Nov 2016 16:38:53 GMT
ENV OWNER=
# Thu, 03 Nov 2016 16:38:53 GMT
ENV USERFILE=eggdrop.user
# Thu, 03 Nov 2016 16:38:53 GMT
ENV CHANFILE=eggdrop.chan
# Thu, 03 Nov 2016 16:38:54 GMT
WORKDIR /home/eggdrop/eggdrop
# Thu, 03 Nov 2016 16:38:54 GMT
EXPOSE 3333/tcp
# Thu, 03 Nov 2016 16:38:54 GMT
COPY file:655c2fd77a7cf08b712ee33a15d7dbd177b8489a67560628236c68c2cc66aa58 in /home/eggdrop/eggdrop 
# Thu, 03 Nov 2016 16:38:55 GMT
COPY file:919804e5ddd4c807c178caccfed03e9d75a459fe0f744c3a1ada109817cb44ec in /home/eggdrop/eggdrop/scripts/ 
# Thu, 03 Nov 2016 16:38:55 GMT
ENTRYPOINT ["/home/eggdrop/eggdrop/entrypoint.sh"]
# Thu, 03 Nov 2016 16:38:55 GMT
CMD ["eggdrop.conf"]
```

-	Layers:
	-	`sha256:3690ec4760f95690944da86dc4496148a63d85c9e3100669a318110092f6862f`  
		Last Modified: Tue, 18 Oct 2016 20:32:39 GMT  
		Size: 2.3 MB (2312958 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6b861641dff653ecbefedada65f0bf6cf61d9d50bf22961fb8c9f5109e75ac1d`  
		Last Modified: Tue, 18 Oct 2016 23:13:24 GMT  
		Size: 1.3 KB (1271 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2da32df17b38a3fe46cfcb562e71a4d0d76ceb7e9da17199a80e3111ed2b7e28`  
		Last Modified: Tue, 18 Oct 2016 23:13:24 GMT  
		Size: 7.9 KB (7928 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:54031bfb603d1f5c5119e53a22c56302508673209bb8f5faae43254f0e46aa78`  
		Last Modified: Thu, 03 Nov 2016 16:39:50 GMT  
		Size: 6.0 MB (5958595 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a5058a4024acc67ea88af44abd52db89fd5a23c68d6b707482bb880b530a30bb`  
		Last Modified: Thu, 03 Nov 2016 16:39:48 GMT  
		Size: 1.6 KB (1559 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:91e1de3a2fb41e3c526a9f529c32f6f9fc0333e594b0b73a73c9d976d97c6c76`  
		Last Modified: Thu, 03 Nov 2016 16:39:47 GMT  
		Size: 698.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
