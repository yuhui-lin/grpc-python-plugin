FROM golang:1.13.4-alpine3.10

RUN apk --no-cache add make bash git automake autoconf libtool build-base

ARG PLUGIN_VERSION=v1.22.1
RUN git clone --branch $PLUGIN_VERSION --recursive https://github.com/grpc/grpc /grpc
RUN mkdir -p /grpc/m4 && make -C /grpc grpc_python_plugin
RUN cp /grpc/bins/opt/grpc_python_plugin /bin/grpc_python_plugin