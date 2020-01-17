FROM golang:1.13-buster

RUN go get github.com/shuLhan/go-bindata/cmd/go-bindata \
 && go get -d github.com/grafana/carbon-relay-ng/... \
 && cd /go/src/github.com/grafana/carbon-relay-ng \
 && make \
 && install carbon-relay-ng /usr/local/sbin/

COPY carbon-relay-ng.ini /etc/carbon-relay-ng/

CMD ["/usr/local/sbin/carbon-relay-ng", "/etc/carbon-relay-ng/carbon-relay-ng.ini"]
