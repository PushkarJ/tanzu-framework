# Copyright 2021 VMware, Inc. All Rights Reserved.
# SPDX-License-Identifier: Apache-2.0

.DEFAULT_GOAL := help

ROOT_DIR	:= $(dir $(shell pwd))

# Image URL for simple app templates image
IMG ?= simple-app-templates:latest

## --------------------------------------
## Help
## --------------------------------------

help: ## Display this help
	@awk 'BEGIN {FS = ":.*##"; printf "\nUsage:\n  make \033[36m<target>\033[0m\n"} /^[a-zA-Z_-]+:.*?##/ { printf "  \033[36m%-15s\033[0m %s\n", $$1, $$2 } /^##@/ { printf "\n\033[1m%s\033[0m\n", substr($$0, 5) } ' $(MAKEFILE_LIST)

## --------------------------------------
## Build simple app templates 
## --------------------------------------

.PHONY: template-image
template-image: ## Build template image
	docker build -t $(IMG) .
