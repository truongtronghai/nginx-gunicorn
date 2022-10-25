FROM ubuntu

RUN apt update && apt install -y python3

RUN apt install -y python3-pip python3-dev default-libmysqlclient-dev build-essential

RUN apt install -y nano

COPY requirements.txt /requirements.txt

RUN pip install -r requirements.txt

RUN django-admin startproject djapp

WORKDIR /djapp

RUN cd /djapp

EXPOSE 8000/tcp

CMD ["gunicorn","-b 0.0.0.0:8000", "--reload","djapp.wsgi"]