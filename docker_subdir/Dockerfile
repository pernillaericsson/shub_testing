FROM ubuntu:16.04


LABEL description = "Testing automated builds"
MAINTAINER "Pernilla" pernilla@email.com

# Use bash as shell
SHELL ["/bin/bash", "-c"]

# Set workdir
WORKDIR /test

# Install necessary tools
RUN apt-get update && \
    apt-get install -y --no-install-recommends bzip2 \
		ca-certificates \
		curl \
		fontconfig \
		git \
		language-pack-en \
		tzdata \
		vim \
		unzip \
		wget \
		&& apt-get clean

# Install Miniconda and add to PATH
RUN curl https://repo.continuum.io/miniconda/Miniconda3-4.7.12.1-Linux-x86_64.sh -O && \
	bash Miniconda3-4.7.12.1-Linux-x86_64.sh -bf -p /usr/miniconda3/ && \
	rm Miniconda3-4.7.12.1-Linux-x86_64.sh

# Add conda to PATH and set locale
ENV PATH="/usr/miniconda3/bin:${PATH}"
ENV LC_ALL en_US.UTF-8
ENV LC_LANG en_US.UTF-8


CMD /bin/bash



