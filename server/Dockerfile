FROM ubuntu:14.04

ENV http_proxy="http://21.158.16.239:8080"
ENV https_proxy="https://21.158.16.239:8080"


WORKDIR app

RUN apt-get update && apt-get install -y \
    pkg-config \
    libpng-dev \
    libjpeg8-dev \
    libfreetype6-dev \
    libblas-dev \
    liblapack-dev \
    libatlas-base-dev \
    gfortran \
    python \
    python-dev \
    python-pip
   # curl && \
   # curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash - && \
   # apt-get install -y nodejs


RUN pip install -U https://storage.googleapis.com/tensorflow/linux/cpu/tensorflow-0.12.1-cp27-none-linux_x86_64.whl

COPY ./requirements.txt /app/
RUN pip install -r /app/requirements.txt

COPY . .

#WORKDIR /src/static/
#RUN npm install && npm run build


WORKDIR /app/
EXPOSE 8080
ENTRYPOINT ["python", "server.py"]

