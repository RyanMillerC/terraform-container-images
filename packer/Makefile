IMG := localhost/packer
TAG := light-1.11.0-custom-2
FILE_NAME := packer_${TAG}

.PHONY: build
build:
	podman build -t "${IMG}:${TAG}" .

.PHONY: bundle
bundle:
	podman save "${IMG}:${TAG}" > "${FILE_NAME}.tar"
	gzip -9 < "${FILE_NAME}.tar" > "${FILE_NAME}.tar.gz"
	base64 "${FILE_NAME}.tar.gz" > "${FILE_NAME}.tar.gz.64"
