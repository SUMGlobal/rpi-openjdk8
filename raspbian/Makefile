DOCKER_IMAGE_VERSION=8-jdk
DOCKER_IMAGE_NAME=sumglobal/rpi-openjdk
DOCKER_IMAGE_TAGNAME=$(DOCKER_IMAGE_NAME):$(DOCKER_IMAGE_VERSION)

default: build

build:
	docker run --rm --privileged multiarch/qemu-user-static:register --reset
	docker build --no-cache -t $(DOCKER_IMAGE_NAME):8 .

tag:
	docker tag $(DOCKER_IMAGE_NAME):8 $(DOCKER_IMAGE_NAME):jdk
	docker tag $(DOCKER_IMAGE_NAME):8 $(DOCKER_IMAGE_NAME):8-jdk
	docker tag $(DOCKER_IMAGE_NAME):8 $(DOCKER_IMAGE_NAME):8u40
	docker tag $(DOCKER_IMAGE_NAME):8 $(DOCKER_IMAGE_NAME):8u40-jdk

push:
	docker push $(DOCKER_IMAGE_TAGNAME)
	docker push $(DOCKER_IMAGE_NAME)

