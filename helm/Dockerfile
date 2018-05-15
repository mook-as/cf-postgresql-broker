# Dockerfile for cf-postgresql-broker
FROM golang:1.9 AS builder
ARG package=github.com/Altoros/cf-postgresql-broker
ADD . /go/src/${package}
RUN mkdir /out
RUN go build -o /cf-postgresql-broker ${package}

FROM opensuse
COPY --from=builder /cf-postgresql-broker /
ENTRYPOINT [ "/cf-postgresql-broker" ]
