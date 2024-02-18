FROM python:3.9.1

RUN apt-get update && \
  apt-get install -y wget && \
  rm -rf /var/lib/apt/lists/* && \
  pip install pandas sqlalchemy psycopg2 pyarrow

WORKDIR /app
COPY ingest_data.py ingest_data.py 

ENTRYPOINT [ "python", "ingest_data.py" ]
CMD ["--user", "root", "--password", "root", "--host", "pgdatabase", "--port", "5432", "--db", "ny_taxi", "--table_name", "yellow_taxi_data", "--url", "https://d37ci6vzurychx.cloudfront.net/trip-data/yellow_tripdata_2023-01.parquet"]
