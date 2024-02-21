FROM mysql:8.0.33
# can be overwritten in docker-compose
ENV MYSQL_ROOT_PASSWORD="dummypw" 
# can be overwritten in docker-compose
ENV MYSQL_DATABASE="accounts"
# not strictly required
VOLUME [ "/var/lib/mysql" ]
COPY db_backup.sql /docker-entrypoint-initdb.d/
EXPOSE 3306