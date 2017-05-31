DOCKER_IMAGE_VERSION=8-jre-alpine
DOCKER_IMAGE_NAME=sumglobal/rpi-openjdk
DOCKER_IMAGE_TAGNAME=$(DOCKER_IMAGE_NAME):$(DOCKER_IMAGE_VERSION)

default: build

build:
	docker build --no-cache -t $(DOCKER_IMAGE_TAGNAME) .

tag:
	docker tag $(DOCKER_IMAGE_TAGNAME) $(DOCKER_IMAGE_NAME):8-alpine

push:
	docker push $(DOCKER_IMAGE_TAGNAME)
	docker push $(DOCKER_IMAGE_NAME)

