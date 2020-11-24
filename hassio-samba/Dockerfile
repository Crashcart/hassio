ARG BASE_IMAGE=debian:buster-slim
FROM $BASE_IMAGE
#ARG BUILD_FROM
#FROM $BUILD_FROM
LABEL maintainer="sid.lucas@gmail.com"

#ARG DEBIAN_FRONTEND=noninteractive
ARG LANG=C.UTF-8
ARG LC_ALL=C.UTF-8
RUN apt-get update -y \
	&& apt-get install -y  cifs-utils samba \
	&& apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*
	
ENV LANG C.UTF-8

# Copy data for add-on
COPY run.sh /
RUN chmod a+x /run.sh
COPY config.json /
CMD [ "/run.sh" ]