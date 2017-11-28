FROM ubuntu

RUN apt-get update && apt-get install -y curl
COPY ./init.json /init.json

CMD curl -XPUT 'elasticsearch:9200/shakespeare?pretty' -H 'Content-Type: application/json' -d'\
{\
 "mappings": {\
  "doc": {\
   "properties": {\
    "speaker": {"type": "keyword"},\
    "play_name": {"type": "keyword"},\
    "line_id": {"type": "integer"},\
    "speech_number": {"type": "integer"}\
   }\
  }\
 }\
}\
'

CMD curl -H 'Content-Type: application/x-ndjson' -XPOST 'elasticsearch:9200/shakespeare/doc/_bulk?pretty' --data-binary @init.json
