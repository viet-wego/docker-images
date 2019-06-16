FROM node:10-alpine
LABEL maintainer="tdviet12@gmail.com"
RUN npm install react-scripts@3.0.1 -g --silent

RUN apk add --no-cache alpine-sdk && \
    cd /tmp && \
    curl -s -LO https://github.com/jpmens/jo/releases/download/1.2/jo-1.2.tar.gz && \
    tar xzf jo-1.2.tar.gz && \
    cd jo-1.2 && \
    ./configure && \
    make check && \
    make install && \
    apk del alpine-sdk && \
    rm -rf /tmp/* /var/lib/apt/lists/*
