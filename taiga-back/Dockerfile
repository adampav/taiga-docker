# Base System
FROM python:3.5

RUN \
  apt-get update && \
  apt-get install -y build-essential binutils-doc autoconf flex bison libjpeg-dev && \
  apt-get install -y libfreetype6-dev zlib1g-dev libzmq3-dev libgdbm-dev libncurses5-dev && \
  apt-get install -y automake libtool libffi-dev curl git tmux gettext && \
  apt-get install -y circus && \
  apt-get install git python3-dev python-dev python-pip virtualenvwrapper

# Create taiga user
RUN \
  adduser taiga
  adduser taiga sudo


# Download the code
RUN \
  su - taiga
  git clone https://github.com/taigaio/taiga-back.git taiga-back
  cd taiga-back
  git checkout stable
