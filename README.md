# SPAR Postgres Database Documentation

- SPAR Github Repo: https://github.com/bcgov/nr-spar
- SPAR Schema Spy Live: add here

## How to generate a new version
  1. Download Schema Spy: https://github.com/schemaspy/schemaspy/releases
  2. Download Postgre JDBC jar Driver: https://jdbc.postgresql.org/download/
  3. Start spar on docker
  4. Get the database container IP: docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' database
  5. Run the magic command:
  java -jar ./schemaspy-6.2.4.jar \
      -t pgsql11 \
      -dp ./postgresql-42.7.3.jar \
      -db postgres \
      -host 172.20.0.2 \
      -port 5432 \
      -u postgres \
      -p default \
      -s spar \
      -o ./output

Here's how to get a running Dcoker container IP address:
```bash
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' database
```
