# Base System
FROM python:3.5

RUN \
  apt-get update && \
  apt-get install -y build-essential binutils-doc autoconf flex bison libjpeg-dev && \
  apt-get install -y libfreetype6-dev zlib1g-dev libzmq3-dev libgdbm-dev libncurses5-dev && \
  apt-get install -y automake libtool libffi-dev curl git tmux gettext && \
  apt-get install -y git python3-dev python-dev python-pip

# Create taiga user
RUN \
  mkdir -p /opt/taiga && \
  mkdir -p /opt/taiga/media /opt/taiga/static /opt/taiga/logs && \
  useradd -d /opt/taiga taiga

# Download the code
RUN \
  su - taiga && \
  git clone https://github.com/taigaio/taiga-back.git /opt/taiga/taiga-back && \
  cd /opt/taiga/taiga-back && \
  git checkout stable && \
  pip install -r requirements.txt
  

# Populate Database + Sample Data


# Copy Configuration
