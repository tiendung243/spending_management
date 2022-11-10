FROM python:3.6.15-slim-buster as intermediate
RUN apt-get update && apt-get install -y python3-pip

RUN mkdir /opt/app
ENV PYTHONPATH /opt/app
ENV PYTHONUNBUFFERED=1

WORKDIR /opt/app

COPY ./requirements.txt ./requirements.txt
RUN pip install --upgrade pip
RUN pip install --no-cache-dir -r requirements.txt

COPY . ./

COPY ./run.sh ./run.sh

RUN chmod +x ./run.sh

ENTRYPOINT ["./run.sh"]