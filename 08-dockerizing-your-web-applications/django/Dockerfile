FROM python:2.7-alpine

RUN mkdir /app
WORKDIR /app

COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

COPY . .

RUN python manage.py collectstatic --noinput

LABEL maintainer="Aymeric Scherrer"

CMD gunicorn -c gunicorn.py "hello.wsgi:application"
