#!/usr/bin/make -f
IMAGE := movie88
VERSION := latest

.PHONY: all build rebuild shell run

# ------------------------------------------------------------------------------

all: rebuild run

# 建置 image
build:
	docker build -f Dockerfile -t=$(IMAGE):$(VERSION) ..

# 不使用 cache 建置 image
rebuild:
	docker build -f Dockerfile -t=$(IMAGE):$(VERSION) --no-cache ..

# 執行並使用 shell 進入 container
shell:
	docker run --rm --name $(IMAGE) -it -p 8081:80 $(IMAGE):$(VERSION) bash

# 執行 container
run:
	docker run --rm --name $(IMAGE) -it -p 8081:80 $(IMAGE):$(VERSION) 