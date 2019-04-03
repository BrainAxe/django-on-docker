FROM python:3.7-alpine
LABEL maintainer="tanzimrizwan@outlook.com"

ENV PYTHONUNBUFFERED 1 

COPY ./requirements.txt /requirements.txt 

RUN apk add --no-cache --virtual .build-deps \
    ca-certificates gcc postgresql-dev linux-headers musl-dev \
    libffi-dev jpeg-dev zlib-dev \
    && pip install -r requirements.txt



RUN mkdir /usr/src/app 
WORKDIR /usr/src/app
COPY . /usr/src/app/ 



RUN adduser -D tanzim 
RUN chown -R tanzim /usr/src/app/
USER tanzim

