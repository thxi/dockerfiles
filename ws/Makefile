build:
	xauth list > tmp-cookie
	./cookie
	docker build -t wireshark .

run:
	docker run -i -t --rm \
		-e DISPLAY=$(DISPLAY) \
		-v /tmp/.X11-unix:/tmp/.X11-unix:ro \
		--net=host \
		--device /dev/dri \
		-v /dev/shm:/dev/shm \
		-v /dev/snd:/dev/snd \
		--privileged \
		wireshark
