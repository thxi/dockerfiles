build:
	docker build -t r .

run:
	docker run -it --rm -p1337:8888 \
	-v$(shell pwd):/home/rstudio \
	r

build-rstudio:
	docker pull rocker/rstudio

run-rstudio:
	docker run --rm \
	-p 1337:8787 \
	-e PASSWORD=123 \
	rocker/rstudio
