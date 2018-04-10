build:
	docker build \
		-t "img_{{ cookiecutter.service_name }}:latest" \
		-f Dockerfile .

version: build
	docker run -it --rm \
		{{ cookiecutter.service_name }} \
		sh -c "echo \"console.log('autobahn-' + require('autobahn').version + ' is installed');\" | node"

start: build
	docker run -it --rm \
		--name {{ cookiecutter.service_name }} \
		--user {{ cookiecutter.uid }} \
		"img_{{ cookiecutter.service_name }}:latest"
