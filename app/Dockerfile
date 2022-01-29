FROM python:3.8-alpine

# set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1
ENV DEBUG 0

COPY ./requirements.txt /requirements.txt

RUN apk add --no-cache --virtual .build-deps \
    ca-certificates gcc postgresql-dev linux-headers musl-dev \
    libffi-dev jpeg-dev zlib-dev \
    && pip install -r requirements.txt



RUN mkdir /usr/src/app
COPY . /usr/src/app/
WORKDIR /usr/src/app


RUN adduser -D django
RUN chown -R django:django /usr/src/app
RUN chmod 755 /usr/src/app
USER django

