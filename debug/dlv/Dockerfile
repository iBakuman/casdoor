ARG GO_VERSION=${GO_VERSION:-1.22.5}

FROM golang:${GO_VERSION}-bullseye

ENV CGO_ENABLED=1
ENV DELVE_PORT=40000

RUN apt-get update \
    && apt-get install -y --no-install-recommends inotify-tools psmisc \
    && go install github.com/go-delve/delve/cmd/dlv@latest

COPY entrypoint.sh /entrypoint.sh

EXPOSE $DELVE_PORT

ENTRYPOINT ["/entrypoint.sh"]
