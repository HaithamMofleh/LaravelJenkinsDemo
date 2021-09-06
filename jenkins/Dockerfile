FROM jenkins/jenkins:2.257-centos7
USER root
RUN yum install epel-release -y

RUN yum install -y yum-utils
RUN yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
RUN yum install -y docker-ce docker-ce-cli containerd.io
# RUN chmod 666 /var/run/docker.sock

RUN rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-7.rpm
RUN yum --enablerepo=remi-php74 install php php-mbstring php-xml php-pdo php-pdo_mysql php-xdebug -y
RUN yum update -y
RUN cd /tmp
RUN curl -sS https://getcomposer.org/installer | php

RUN mv composer.phar /usr/local/bin/composer
