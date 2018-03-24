# ksql

## ksql server setup
- Download KSQL from https://github.com/confluentinc/ksql/releases/tag/v0.4
- Unzip and go to KSQL/Config folder, edit ksqlserver.properties and set bootstrap.servers
- Run server: ./bin/ksql-server-start ./config/ksqlserver.properties
- Open another window and run KSQL Client: ./bin/ksql-cli remote http://localhost:8080

## Create Table and Streams
- https://github.com/confluentinc/ksql/blob/v0.5/docs/syntax-reference.md#syntax-reference

## Comands
- CREATE TABLE resvents (ci VARCHAR, pl VARCHAR) WITH (key='ci', kafka_topic='qa-shore-res-vas.voyage-reservation', value_format='JSON');

-  select ci, EXTRACTJSONFIELD(pl, '$.guestDetails[0].guestId') from resvents limit 5;

- SET 'auto.offset.reset' = 'earliest';
