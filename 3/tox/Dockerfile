FROM python:buster
LABEL maintainer="Forest Keepers <Jeroen.knoops@philips.com>"

RUN apt-get update && \
    apt-get install -y git netcat curl jq wget

RUN pip install tox==3.20.1

ADD REPO .
ADD TAGS .

CMD ["/bin/bash"]
