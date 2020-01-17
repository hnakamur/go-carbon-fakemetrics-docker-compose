FROM golang:1.13-buster

RUN go get -d github.com/lomik/go-carbon \
 && cd /go/src/github.com/lomik/go-carbon \
 && make \
 && install go-carbon /usr/local/sbin/ \
 && useradd -r carbon

COPY go-carbon.conf storage-aggregation.conf storage-schemas.conf /etc/go-carbon/

CMD ["/usr/local/sbin/go-carbon", "-config", "/etc/go-carbon/go-carbon.conf"]
