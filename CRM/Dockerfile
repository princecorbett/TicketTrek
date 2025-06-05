FROM python:3.11-bullseye

ENV PYTHONBUFFERED=1

WORKDIR /CRM

# Install system dependencies for psycopg2
RUN apt-get update && apt-get install -y libpq-dev gcc

COPY requirements.txt requirements.txt

RUN pip install -r requirements.txt

COPY . .

CMD gunicorn CRM.wsgi:application --bind 0.0.0.0:8000

EXPOSE 8000
