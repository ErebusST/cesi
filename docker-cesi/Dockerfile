FROM ubuntu:16.04

MAINTAINER ErebusST "situbin@foxmail.com"


ENV CESI_USERINFO_FILE /cesi/userinfo.db

RUN apt-get update && apt-get -y install sqlite3 python python-flask && \
    apt-get -y install git && \
    git clone https://github.com/ErebusST/cesi && \
    mkdir /var/log/cesi && \
    touch $CESI_USERINFO_FILE && \
    sqlite3 $CESI_USERINFO_FILE < cesi/userinfo.sql

EXPOSE 5000 

ENTRYPOINT ["python"]

CMD ["/cesi/cesi/web.py"]
