FROM registry.access.redhat.com/rhel7:7.5

# subcription manager
RUN subscription-manager register --username comit-dev03 --password 4WwcgHM@p7HF2fw --auto-attach
RUN subscription-manager repos --enable=rhel-7-server-rpms

# install nodejs
RUN yum -y install gcc-c++ make
RUN curl -sL https://rpm.nodesource.com/setup_12.x | bash -
RUN yum -y install nodejs

# install supervisor
RUN yum -y install python-setuptools && mkdir -p /var/log/supervisor && easy_install supervisor

# unregister redhat subcription
RUN subscription-manager unregister

# Set default work directory
WORKDIR /var/www
