#Version: 1.0.0

FROM centos:7

MAINTAINER df "duanfeisj@tuniu.com"

USER root

RUN yum install curl openssh-server
RUN systemctl enable sshd
RUN systemctl start sshd
RUN yum install postfix
RUN systemctl enable postfix
RUN systemctl start postfix
RUN firewall-cmd --permanent --add-service=http
RUN systemctl reload firewalld

RUN curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.rpm.sh | sudo bash
RUN yum install gitlab-ce

RUN sudo gitlab-ctl reconfigure

CMD ls -l -a
