FROM debian:stretch

ARG ANSIBLE_VERSION=2.1.2.0-0.2.rc2

RUN apt-get update -y
RUN apt-get install -y supervisor build-essential libffi-dev libssl-dev python-pip python-dev
RUN pip install --upgrade setuptools \
    && pip install http://releases.ansible.com/ansible/ansible-${ANSIBLE_VERSION}.tar.gz

COPY data/initctl_faker .
COPY data/systemctl_faker .
COPY data/service_faker .
RUN chmod +x initctl_faker && rm -fr /sbin/initctl && ln -s /initctl_faker /sbin/initctl
RUN chmod +x systemctl_faker && rm -fr /bin/systemctl && ln -s /systemctl_faker /bin/systemctl
RUN chmod +x service_faker && mv /usr/sbin/service /usr/sbin/service_real && ln -s /service_faker /usr/sbin/service