FROM registry.access.redhat.com/rhel7
MAINTAINER scollier <scollier@redhat.com>

RUN yum repolist all
RUN yum -y install hostname net-tools psmisc mariadb-server mariadb; yum clean all

ADD ./config_mariadb.sh /config_mariadb.sh

RUN chmod 755 /config_mariadb.sh
RUN /config_mariadb.sh

EXPOSE 3306

CMD ["/usr/bin/mysqld_safe"]
