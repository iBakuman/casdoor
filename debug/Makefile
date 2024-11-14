export PWD := $(shell pwd)
export CASDOOR_SRC_DIR=$(realpath ..)
export CASDOOR_DEBUG_PORT=1827
export GO_VERSION=1.22.5

.PHONY: start-debug
start-debug:
	@echo "CASDOOR_SRC_DIR: $(CASDOOR_SRC_DIR)"
	@docker compose up

.PHONY: build-dlv
build-dlv:
ifeq ($(GO_VERSION),)
	$(error GO_VERSION is empty. Please provide a value for GO_VERSION)
endif
	@echo "Building dlv image for Go version $(GO_VERSION)"
	@docker build -t ibakuman/go-debugger:$(GO_VERSION) -f dlv/Dockerfile --build-arg GO_VERSION=$(GO_VERSION) dlv
