FROM golang:alpine
MAINTAINER ryan.carmichael@elabsolutions.com
EXPOSE 18888
ENV SACONFIGFILE /opt/sa/config.json
ENV SAVERSION 0.1.0
ENV GOLANG_DOWNLOAD_URL https://github.com/eLabSolutions/statusAggregator/releases/download/v$SAVERSION/statusAggregator-linux-amd64
RUN apk add --no-cache curl
RUN mkdir /lib64 && ln -s /lib/libc.musl-x86_64.so.1 /lib64/ld-linux-x86-64.so.2
RUN curl -fsSL "$GOLANG_DOWNLOAD_URL" -o /go/bin/statusAggregator
RUN chmod u+x /go/bin/statusAggregator
CMD statusAggregator
