FROM debian:bullseye
LABEL maintainer="Forest Keepers <Jeroen.knoops@philips.com>"

ENV PYTHON_VERSION 3.11.2

RUN apt-get update && \
    apt-get install -y \
      git netcat curl jq wget default-jdk && \
    apt-get install -y --no-install-recommends \
      make build-essential libssl-dev zlib1g-dev libbz2-dev \
      libreadline-dev libsqlite3-dev ca-certificates llvm \
      libncurses5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev \
      libffi-dev liblzma-dev mecab-ipadic-utf8

# Set-up necessary Env vars for PyEnv
ENV PYENV_ROOT /root/.pyenv
ENV PATH $PYENV_ROOT/shims:$PYENV_ROOT/bin:$PATH

# Install pyenv
RUN set -ex \
    && curl https://pyenv.run | bash \
    && pyenv update \
    && pyenv install $PYTHON_VERSION \
    && pyenv global $PYTHON_VERSION \
    && pyenv rehash

RUN pip install --upgrade pip

ADD REPO .
ADD TAGS .

CMD ["/bin/bash"]
