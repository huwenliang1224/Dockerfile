FROM daocloud.io/library/centos:centos7

RUN yum install -y git wget java-1.8.0-openjdk 
ENV JAVA_HOME /usr/lib/jvm/jre-1.8.0-openjdk/
RUN wget http://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo
RUN yum -y install apache-maven

RUN mkdir /workspace/
WORKDIR /workspace/

RUN git clone https://github.com/huwenliang1224/web.git

WORKDIR /workspace/web
RUN mvn clean package -DskipTests

RUN cp /workspace/web/target/web.jar /workspace/

EXPOSE 8080

WORKDIR /workspace/

CMD ["java","-jar","web.jar"]

