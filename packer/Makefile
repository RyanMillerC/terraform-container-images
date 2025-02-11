IMG := localhost/packer
TAG := light-1.12.0-custom
FILE_NAME := packer_${TAG}

.PHONY: build
build:
	podman build --platform linux/amd64 --tag "${IMG}:${TAG}" .

.PHONY: bundle
bundle:
	podman save "${IMG}:${TAG}" > "${FILE_NAME}.tar"
	gzip -9 < "${FILE_NAME}.tar" > "${FILE_NAME}.tar.gz"
	base64 "${FILE_NAME}.tar.gz" > "${FILE_NAME}.tar.gz.64"
