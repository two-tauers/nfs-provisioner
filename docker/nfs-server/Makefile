.DEFAULT_GOAL := help

VERSION := 0.1.0
SOURCE_NAME ?= nfs-server

.PHONY: build
build: pull-source-repo ## Build and push the image to docker hub
	@echo "..... Building docker image"
	@docker buildx build --platform linux/arm64,linux/arm/v7 --build-arg VERSION=${VERSION} -t timberhill/nfs-server:${VERSION} --push ${SOURCE_NAME}
	@docker buildx build --platform linux/arm64,linux/arm/v7 --build-arg VERSION=${VERSION} -t timberhill/nfs-server:latest --push ${SOURCE_NAME}

.PHONY: help
help: ## Display this help
	@echo "Usage:\n  make \033[36m<target>\033[0m"
	@awk 'BEGIN {FS = ":.*##"}; \
		/^[a-zA-Z0-9_-]+:.*?##/ { printf "  \033[36m%-15s\033[0m %s\n", $$1, $$2 } \
		/^##@/ { printf "\n\033[1m%s\033[0m\n", substr($$0, 5) } \
		/^###@/ { printf "\n\033[1m%s\033[0m\n", substr($$0, 5) } ' $(MAKEFILE_LIST)
