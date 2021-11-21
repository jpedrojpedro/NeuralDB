FROM python:3.8.12-slim-buster

COPY ./sec /home/airflow/sec/
COPY ./plugins /home/airflow/plugins/
COPY ./entrypoint.sh /home/airflow/

RUN pip3 install --no-cache-dir --upgrade pip \
 && pip3 install tableauserverclient==0.14.1 \
 && pip3 install gspread==3.6.0 \
 && pip3 install pyarrow==0.16.0 \
 && pip3 install s3fs==0.4.0 \
 && pip3 install oauth2client==4.1.3

RUN sudo chmod +x /home/airflow/entrypoint.sh
ENTRYPOINT ["/home/airflow/entrypoint.sh"]
