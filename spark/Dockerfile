FROM python:3.9

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

WORKDIR /workspace

COPY requirements.txt .

RUN apt-get update && apt-get -y install software-properties-common 
RUN apt-add-repository 'deb http://security.debian.org/debian-security stretch/updates main'
RUN apt-get update
RUN apt-get -y install openjdk-11-jdk
RUN pip install -r requirements.txt

COPY . .

EXPOSE 8888

ENTRYPOINT ["sh", "entrypoint.sh"]