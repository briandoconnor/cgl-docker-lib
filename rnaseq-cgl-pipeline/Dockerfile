FROM ubuntu:14.04

# File Author / Maintainer
MAINTAINER John Vivian <jtvivian@gmail.com>

RUN apt-get update && apt-get install -y \
    git \
    python-dev \
    python-pip \
    wget \
    curl \
    apt-transport-https \
    ca-certificates

# Get the Docker binary
#RUN wget https://get.docker.com/builds/Linux/x86_64/docker-DOCKERVER -O /usr/local/bin/docker
#RUN chmod u+x /usr/local/bin/docker

# To install, run the following commands as root:
RUN curl -fsSLO https://get.docker.com/builds/Linux/x86_64/docker-1.12.3.tgz && tar --strip-components=1 -xvzf docker-1.12.3.tgz -C /usr/local/bin
RUN chmod u+x /usr/local/bin/docker

# Install Toil
RUN pip install toil==3.3.1

# Install BPL
RUN pip install bd2k-python-lib==1.14a1.dev29

# Install toil-scripts
RUN pip install toil-scripts==2.0.10

COPY wrapper.py /opt/rnaseq-pipeline/
COPY README.md /opt/rnaseq-pipeline/

#ENTRYPOINT ["python", "/opt/rnaseq-pipeline/wrapper.py"]
#CMD ["--help"]
