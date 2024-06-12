IMG := localhost/tfc-agent
TAG := 1.15.2-custom
FILE_NAME := tfc-agent_${TAG}

.PHONY: build
build:
        podman build -t "${IMG}:${TAG}" .

.PHONY: bundle
bundle:
        podman save "${IMG}:${TAG}" > "${FILE_NAME}.tar"
        gzip -9 < "${FILE_NAME}.tar" > "${FILE_NAME}.tar.gz"
        base64 "${FILE_NAME}.tar.gz" > "${FILE_NAME}.tar.gz.64"
