FROM alpine:3.7
WORKDIR /usr/local/bin
RUN apk add --update bash
RUN \
    mkdir tmp && \
    wget -c https://github.com/cayleygraph/cayley/releases/download/v0.7.7/cayley_0.7.7_linux_amd64.tar.gz -O - | \
      tar -xvz -C tmp/ --strip-components=1 && \
    cp tmp/cayley . && \
    rm -r tmp
COPY cayley.yml cayley.yml
COPY entrypoint.sh entrypoint.sh
EXPOSE 64210
ENTRYPOINT ["/entrypoint.sh"]
