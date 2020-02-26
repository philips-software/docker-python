FROM python:buster
MAINTAINER Forest Keepers <thales.sousa@philips.com>

RUN apt-get update && \
    apt-get install -y git netcat curl jq wget

ADD REPO .
ADD TAGS .

CMD ["/bin/bash"]
