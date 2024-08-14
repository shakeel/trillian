FROM golang:1.23.0-bookworm@sha256:d7fbe2dd57ca07e3ae547228889763d0968e5acdf4037fe36d7894e8e35466f0

RUN apt-get update && \
    apt-get install -y mariadb-client

ADD . /go/src/github.com/google/trillian
WORKDIR /go/src/github.com/google/trillian

# This is used to wait for new MySQL deployments to become ready e.g.
#  ./wait-for-it.sh localhost:3306 -- mysql
RUN ./examples/deployment/scripts/download-wait-for-it.sh

CMD [ 'mysql' ]
