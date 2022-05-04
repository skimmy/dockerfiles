FROM debian:bullseye-slim

RUN groupadd --gid 1000 mike \
  && useradd --uid 1000 --gid mike --shell /bin/bash --create-home mike

RUN apt-get update && apt-get install -y \ 
	bash \
	g++ \
	cmake \
	git \
	libboost-all-dev 

RUN git clone --recursive https://gitlab.com/skimmy/average-edit-distance.git && \
	cd average-edit-distance && \
	cmake . && \
	make && \
	cp aed /usr/bin && \
	cd .. && \
	rm -r average-edit-distance

CMD bash
