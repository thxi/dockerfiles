build:
	docker pull rocker/rstudio

run:
	docker run \
	-p 8787:8787 \
	-e PASSWORD=123 \
	-v$(shell pwd):/home/rstudio \
	--name rstudio \
	rocker/rstudio

resume:
	docker attach \
	$(shell docker start rstudio)

stop:
	docker stop rstudio

build-jupyter:
	docker build -t r .

run-jupyter:
	docker run -it --rm -p1337:8888 \
	-v$(shell pwd):/home/rstudio \
	r
