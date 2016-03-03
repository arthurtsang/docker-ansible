FROM gliderlabs/alpine:3.3

MAINTAINER Arthur Tsang <amaryllis.arthur@gmail.com>

ENV ANSIBLE_VERSION 2.0.0.2
ENV ANSIBLE_CONFIG /ansible.cfg

RUN apk add --update --no-cache python py-pip py-crypto openssh-client sshpass libtool python-dev automake autoconf alpine-sdk && \
    pip install --upgrade pip && \
    pip install --upgrade six && \
    pip install pyjq && \
    pip install ansible==${ANSIBLE_VERSION} && \
    apk del libtool python-dev automake autoconf alpine-sdk && \
    chmod 755 /run.sh

ADD ansible.cfg /ansible.cfg
ADD run.sh /run.sh


ENTRYPOINT ["/run.sh"]
