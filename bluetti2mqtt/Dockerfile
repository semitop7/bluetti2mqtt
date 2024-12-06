ARG BUILD_FROM
# ghcr.io/hassio-addons/base-python: 15.0.3 version
FROM $BUILD_FROM

# Copy data for add-on
COPY rootfs /

# Add edge repo that contains bluez 5.79-r0 version
RUN echo 'https://dl-cdn.alpinelinux.org/alpine/edge/main' > /etc/apk/repositories && \
    echo 'https://dl-cdn.alpinelinux.org/alpine/edge/community' >> /etc/apk/repositories

# Install bluetti_mqtt version 0.15.7
RUN apk add --update --no-cache \
    		    bluez=5.79-r0 git \
    && pip install git+https://github.com/semitop7/bluetti_mqtt.git \
	&& rm -rf /var/cache/apk/* /lib/apk/db/* \
	&& chmod a+x /run.sh

CMD [ "/run.sh" ]
