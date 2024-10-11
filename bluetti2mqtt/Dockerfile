ARG BUILD_FROM
FROM $BUILD_FROM

# Copy data for add-on
COPY rootfs /

# Install git
RUN apk add --update --no-cache git

# Install bluetti_mqtt
RUN pip install git+https://github.com/olexandrkucher/bluetti_mqtt \
  && apk add --update --no-cache bluez \
  && rm -rf /var/cache/apk/* /lib/apk/db/* \
  && chmod a+x /run.sh

CMD [ "/run.sh" ]