FROM postgres:9.5
RUN docker-entrypoint.sh
ENV POSTGRES_USER postgres
ENV POSTGRES_PASSWORD 1234
ENV POSTGRES_DB dota

ADD ./dota_dump.sql /docker-entrypoint-initdb.d/

