VERSION?=1.1.1
REGISTRY?=louygan
PROJECT?=openssl-alpine

build:
	docker build . --build-arg version=${VERSION} -t ${REGISTRY}/${PROJECT}:${VERSION}

push: build
	docker push ${REGISTRY}/${PROJECT}:${VERSION}

clean:
	sudo docker rmi -f ${REGISTRY}/${PROJECT}:${VERSION} || true
