FROM python:3.8.3-alpine

RUN apk add --no-cache build-base libffi-dev tzdata\
 && pip --no-cache-dir install aiohttp requests json5 \
 && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
 && echo "Asia/Shanghai" >  /etc/timezone \
 && rm -rf ~/.cache/pip \
 && rm -rf /tmp/* \
 && apk del libffi-dev build-base tzdata

COPY /Docker/entry.sh ./entry.sh

RUN ["chmod", "+x", "./entry.sh"]

ENTRYPOINT ["./entry.sh"]