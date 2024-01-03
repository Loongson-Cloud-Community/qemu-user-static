download:
	wget https://github.com/Loongson-Cloud-Community/qemu-user-static/releases/download/abi2.0/qemu-static-8.2.0-rc2.tar.gz \
	&& tar xf qemu-static-8.2.0-rc2.tar.gz --strip-components=1 \
	&& for file in $(find ./ -name "qemu-*"); do mv $(file) $(file)-static; done
build: download
	docker buildx build --load -t lcr.loongnix.cn/library/qemu-user-static:openeuler -f Dockerfile . \
	&& rm -rf qemu-*
clean:
	rm -rf qemu-*

