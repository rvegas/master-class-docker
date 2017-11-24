FROM mongo

COPY ./init.json /init.json
CMD mongoimport --host mongodb --db dota --collection heroes --type json --file /init.json --jsonArray
