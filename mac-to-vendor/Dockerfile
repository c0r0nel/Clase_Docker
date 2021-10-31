FROM alpine:3.10

LABEL mantainer="amansilla@gmail.com"

ENV TERM xterm

RUN apk update
RUN apk add python2 py2-pip uwsgi uwsgi-python
RUN pip install --upgrade pip
RUN mkdir -p /opt/ip-mac
WORKDIR /opt/ip-mac
COPY src/* /opt/ip-mac/
RUN pip install -r requirements.txt

USER 1000:1000
CMD uwsgi --ini /opt/ip-mac/app.ini

EXPOSE 8000
