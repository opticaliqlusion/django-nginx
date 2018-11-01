FROM python:2
ENV PYTHONUNBUFFERED 1
RUN mkdir /django
RUN mkdir /socks
ADD requirements.txt /django
RUN pip install -r /django/requirements.txt
ADD . /django

WORKDIR /django/mysite
CMD gunicorn --workers 3 --bind unix:/socks/mysite.sock mysite.wsgi
