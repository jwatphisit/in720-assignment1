FROM python:2.7
MAINTAINER Jay Watphisit <jwatphisit@hotmail.com>

ADD . /flaskapp

WORKDIR /flaskapp

RUN apt-get -qqy update

RUN apt-get -qqy install git libcurl4-openssl-dev curl build-essential

RUN pip install flask uwsgi

RUN uwsgi --build-plugin https://github.com/unbit/uwsgi-consul

ENTRYPOINT [ "uwsgi", "--ini", "uwsgi-flaskapp.ini", "--ini", "uwsgi-flaskapp.ini:server1" ]

CMD []
