FROM apache/airflow:2.6.0

COPY requirements.txt /

USER root

RUN mkdir -p /mnt/datatemp && chown airflow:root /mnt/datatemp

USER airflow

RUN pip install --no-cache-dir -r /requirements.txt