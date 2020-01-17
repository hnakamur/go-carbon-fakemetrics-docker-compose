FROM golang:1.13-buster

RUN apt-get update \
 && apt-get install -y libcairo2-dev \
 && go get -d github.com/go-graphite/carbonapi || : \
 && cd /go/src/github.com/go-graphite/carbonapi \
 && make \
 && install carbonapi /usr/local/sbin/

COPY carbonapi.yaml /etc/carbonapi/

CMD ["/usr/local/sbin/carbonapi", "-config", "/etc/carbonapi/carbonapi.yaml"]
