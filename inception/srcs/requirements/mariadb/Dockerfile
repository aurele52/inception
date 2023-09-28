FROM debian:buster

RUN apt-get update \
    && apt-get install -y mariadb-server \
    mariadb-client

COPY ./conf/50-server.cnf /etc/mysql/mariadb.conf.d/
COPY ./tools/script.sh /
RUN chmod +x script.sh

EXPOSE 3306

CMD ["/script.sh"]
