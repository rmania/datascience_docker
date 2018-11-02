FROM debian
LABEL maintainer=@joshuacook
# arg to define an env variable available at runtime
ARG DEBIAN_FRONTEND=noninteractive
# install MINICONDa via RUN
RUN apt-get update --fix-missing && \
    apt-get install -y \
    wget bzip2 ca-certificates \
    libglib2.0-0 libxext6 libsm6 libxrender1
# use TINI, lw solution to solve the 'zmbi' proces problem (see page 96)
RUN apt-get install -y curl grep sed dpkg && \
    TINI_VERSION=`curl https://github.com/krallin/tini/releases/latest | grep -o "/v.*\"" | sed 's:^..\(.*\).$:\1:'` && \
    curl -L "https://github.com/krallin/tini/releases/download/v${TINI_VERSION}/tini_${TINI_VERSION}.deb" > tini.deb && \
    dpkg -i tini.deb && \
    rm tini.deb && \
    apt-get clean
# config the ENV varibale to ensure container run properly
ENV LANG=C.UTF-8 LC_ALL=C.UTF-8
ENV PATH /opt/conda/bin:$PATH
# provide ENTRYPOINT specifying the process to be launched when image is instantiated
# tell docker to run TINI as PID 1
ENTRYPOINT [ "/usr/bin/tini", "--" ]
