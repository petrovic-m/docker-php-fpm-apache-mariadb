FROM mariadb:10.3.22
COPY Import/ /docker-entrypoint-initdb.d
ARG MYSQL_CONTAINER_USER
ARG MYSQL_CONTAINER_GROUP
RUN apt update && apt install vim -y
RUN echo "log_error=/var/log/mysql/mariadb.err" >> /etc/mysql/mariadb.cnf

RUN usermod -u 1000 ${MYSQL_CONTAINER_USER} \
    && groupmod -g 1000 ${MYSQL_CONTAINER_GROUP}