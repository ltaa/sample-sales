FROM postgres:9.6

RUN mkdir -p /data
COPY datadb /data

RUN CUBA_PASSWD="'cuba'"

RUN echo '#!/bin/bash\n\
set -e \n\
psql -v ON_ERROR_STOP=1 --username "$POSTGRES_USER" <<-EOSQL \n\
	CREATE USER cuba WITH password '"'cuba'"';\n\
	CREATE DATABASE sales;\n\
	GRANT ALL PRIVILEGES ON DATABASE sales TO cuba;\n\
EOSQL\n\
psql --username "$POSTGRES_USER" sales < /data/datadb\n'\
>> /docker-entrypoint-initdb.d/init-user-db.sh


ENTRYPOINT ["/docker-entrypoint.sh"]
EXPOSE 5432
CMD ["postgres"]
