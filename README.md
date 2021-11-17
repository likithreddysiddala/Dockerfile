# Dockerfile

FROM centos:latest
RUN yum install java-1.8.0-openjdk -y
RUN mkdir /opt/tomcat
WORKDIR /opt/tomcat
ADD https://dlcdn.apache.org/tomcat/tomcat-10/v10.0.13/bin/apache-tomcat-10.0.13.tar.gz .
RUN tar -xvzf apache-tomcat-10.0.13.tar.gz
RUN mv apache-tomcat-10.0.13/* /opt/tomcat
EXPOSE 8080
CMD ["/opt/tomcat/bin/catalina.sh"."run"]





Docker image creation :
docker build -t image_name .

Docker push commands
docker tag image_name:tag-name username/reponame:tagname

docker push <username>/<reponame>:<tagname>
