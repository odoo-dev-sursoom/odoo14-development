FROM python:3.8

ENV PYTHONUNBUFFERED 1
RUN mkdir /app
WORKDIR /app
COPY requirements.txt /app/
RUN apt-get update -y
RUN apt-get install libevent-dev libsasl2-dev libldap2-dev libssl-dev -y
RUN apt-get install xvfb libfontconfig wkhtmltopdf -y

RUN pip install -r requirements.txt
COPY . /app/
CMD ./odoo-bin -c odoo.local.conf -d odoo-mold --dev=all
