FROM ubuntu:xenial

RUN echo test
RUN apt-get update -y
RUN echo test
RUN apt-get install -y curl

RUN curl -O https://repo.continuum.io/archive/Anaconda3-5.0.1-Linux-x86_64.sh
RUN mv Anaconda3-5.0.1-Linux-x86_64.sh /tmp/Anaconda3-5.0.1-Linux-x86_64.sh
RUN chmod 755 /tmp/Anaconda3-5.0.1-Linux-x86_64.sh

## puts this further up
RUN apt-get install bzip2
RUN /tmp/Anaconda3-5.0.1-Linux-x86_64.sh -b
ENV PATH="/root/anaconda3/bin:${PATH}"
RUN conda update conda

RUN conda create -n tensorflow python=3.5
RUN /root/anaconda3/envs/tensorflow/bin/pip install --ignore-installed --upgrade tensorflow

ENV PATH="/root/anaconda3/envs/tensorflow/bin:${PATH}"

WORKDIR /app
EXPOSE 5000
CMD jupyter lab --port=8899 --ip=0.0.0.0 --allow-root
