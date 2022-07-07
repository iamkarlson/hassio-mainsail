ARG BUILD_FROM
FROM $BUILD_FROM

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# Install deCONZ dependencies
ARG BUILD_ARCH
RUN \
    set -x \
    && apt-get update \
    && apt-get install -y --no-install-recommends \
        curl \
        nginx \
        wget \
        unzip


COPY rootfs /

WORKDIR /code/mainsail
RUN wget -q -O mainsail.zip https://github.com/mainsail-crew/mainsail/releases/latest/download/mainsail.zip 
RUN unzip mainsail.zip 
RUN rm mainsail.zip

CMD ["nginx", "-g", "daemon off;"]
