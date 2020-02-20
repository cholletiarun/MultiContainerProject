#Speciify Base Image.
FROM dockertrainingarun/wm10dockerbaseimage:latest

#switch user to root
USER root

#Download and isntall dependency.
 RUN yum -y install git

# Adding ARG to ingnore the caching for gitclone
ADD "https://www.random.org/cgi-bin/randbyte?nbytes=10&format=h" skipcache

#COPY  jars to /sag/IntegrationServer/instances/default/lib/jars
RUN mkdir /home/tempjars \
 && cd /home/tempjars \
 && git clone https://github.com/cholletiarun/adapterjars.git \ 
 && cp -r /home/tempjars/adapterjars/* /sag/IntegrationServer/instances/default/packages

#COPY  packages /sag/IntegrationServer/instances/default/packages/
RUN mkdir /home/temppacks \
 && cd /home/temppacks \
 && git clone https://github.com/cholletiarun/packages.git \
 && cp -r /home/temppacks/packages/* /sag/IntegrationServer/instances/default/packages
