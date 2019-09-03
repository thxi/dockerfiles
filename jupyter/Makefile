build:
	docker build . -t jupyter-notebook

run:
	docker run \
	-p8888:8888 \
	-v$(shell pwd):/app \
	jupyter-notebook
