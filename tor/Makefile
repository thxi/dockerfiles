build:
	docker build -t tor .

run:
	docker run -d --rm \
		-p 9050:9050 \
		--name torproxy \
		tor