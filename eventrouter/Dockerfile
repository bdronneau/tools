FROM golang:1.19-alpine as builder
ARG GIT_BRANCH
WORKDIR /go/src/github.com/openshift/
RUN apk update && apk add \
        make \
        gcc \
        g++ \
        git
RUN git clone -n https://github.com/openshift/eventrouter \
        && cd eventrouter \
        && git checkout $GIT_BRANCH
WORKDIR /go/src/github.com/openshift/eventrouter
RUN go build .

FROM alpine
COPY --from=builder /go/src/github.com/openshift/eventrouter/eventrouter /bin/eventrouter
CMD ["/bin/eventrouter", "-v", "3", "-logtostderr"]