# to build :
# docker build --tag ex00 .

# to run :
# docker run --rm --interactive --tty ex00

FROM alpine

RUN apk update
RUN apk upgrade
RUN apk add vim

ENTRYPOINT vim
