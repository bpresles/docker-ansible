FROM ubuntu:xenial

ARG ANSIBLE_VERSION=2.1.2.0-0.2.rc2

RUN apt-get update -y
RUN apt-get install -y supervisor build-essential libffi-dev libssl-dev python-pip python-dev
RUN pip install --upgrade setuptools \
    && pip install http://releases.ansible.com/ansible/ansible-${ANSIBLE_VERSION}.tar.gz