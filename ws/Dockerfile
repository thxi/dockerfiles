FROM ubuntu:latest

# Install requirements
RUN apt-get update && apt-get install -y \
	wireshark \
	vim \
	xauth 

# safe space 0_____>_<_____0
#	&& rm -rf /var/lib/apt/lists/*


# why???
# # Add wireshark user
# RUN groupadd -g 1000 wireshark && useradd -u 1000 -g 1000 -G audio,video wireshark \
# 	&& mkdir -p /home/wireshark/ && chown -R wireshark:wireshark /home/wireshark


# # # Run wireshark as non privileged user
# USER wireshark
# WORKDIR /home/wireshark


COPY tmp-cookie .
RUN xauth source tmp-cookie

