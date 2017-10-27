FROM debian:stretch

ARG ANSIBLE_VERSION=2.4.1.0

RUN apt-get update -y
RUN apt-get install -y supervisor build-essential libffi-dev libssl-dev python-pip python-dev
RUN pip install --upgrade setuptools \
    && pip install http://releases.ansible.com/ansible/ansible-${ANSIBLE_VERSION}.tar.gz