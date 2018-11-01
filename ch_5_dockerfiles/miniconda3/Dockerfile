FROM debian
LABEL maintainer=@joshuacook
# arg to define an env variable available at runtime
ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update --fix-missing && \
    apt-get install -y \
    wget bzip2 ca-certificates \
    libglib2.0-0 libxext6 libsm6 libxrender1
