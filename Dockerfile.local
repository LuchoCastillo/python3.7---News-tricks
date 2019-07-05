FROM python:3.7

RUN sh -c "echo 'LANG=en_US.UTF-8\nLC_ALL=en_US.UTF-8' > /etc/default/locale"
RUN apt-get update && apt-get install -y wget software-properties-common \
    python3-dev swig mysql-client mongodb-clients python-pip default-libmysqlclient-dev \
    python-lxml python-setuptools build-essential libmemcached11 libmemcachedutil2 \
    libmemcached-dev libz-dev gosu && rm -rf /var/lib/apt/lists/*

ADD . /app/
WORKDIR /app/

RUN pip install pip -U && pip install --no-binary django -r /app/requirements.txt
