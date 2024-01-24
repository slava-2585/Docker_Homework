FROM python:3.11-slim

RUN mkdir code

WORKDIR code

ADD . /code/

RUN pip install --upgrade pip
RUN pip install -r requirements.txt

ENV SECRET_KEY = '75DMCBSKHJW7*&76594MNVNEO*&^3JNSVYHV'
ENV DEBUG = TRUE

CMD python manage.py makemigrations
CMD python manage.py migrate

CMD gunicorn stocks_products.wsgi:application -b 0.0.0.0:8000