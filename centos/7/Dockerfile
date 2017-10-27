FROM centos:7

ARG ANSIBLE_VERSION=2.1.2.0-0.2.rc2

RUN yum update -y || exit 1
RUN yum install supervisor gcc wget python python-devel libffi-devel openssl-devel -y || exit 1
RUN wget https://bootstrap.pypa.io/get-pip.py || exit 1
RUN python get-pip.py || exit 1
RUN rm -f get-pip.py
RUN pip install --upgrade setuptools \
    && pip install http://releases.ansible.com/ansible/ansible-${ANSIBLE_VERSION}.tar.gz