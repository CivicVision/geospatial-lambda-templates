SHELL = /bin/bash

all: build package

build:
	docker build --tag example:latest .

package:
	docker run \
		-w /var/task/ \
		--name your_name \
		-itd \
		example:latest
	docker cp your_name:/tmp/package.zip package.zip
	docker stop your_name
	docker rm your_name

deploy:
	sls deploy
