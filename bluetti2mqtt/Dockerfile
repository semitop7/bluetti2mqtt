ARG BUILD_FROM
# ghcr.io/hassio-addons/base-python: 18.0.0 version
FROM $BUILD_FROM

# Copy data for add-on
COPY rootfs /

# Install fork bluetti_mqtt version 0.16.1
RUN apk add --no-cache git \
    && pip install --no-cache-dir git+https://github.com/semitop7/bluetti_mqtt.git \
    && chmod a+x /run.sh

CMD [ "/run.sh" ]