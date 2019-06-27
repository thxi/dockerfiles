# docker run -d \
#	--restart always \
#	-v /etc/localtime:/etc/localtime:ro \
#	-p 9050:9050 \
# 	--name torproxy \
# 	tor
#
FROM alpine:latest

RUN apk --no-cache add \
	tor

# expose socks port
EXPOSE 9050

# copy torrc file
COPY torrc.default /etc/tor/torrc.default

# make sure files are owned by tor user
RUN chown -R tor /etc/tor

USER tor

ENTRYPOINT [ "tor" ]
CMD [ "-f", "/etc/tor/torrc.default" ]

