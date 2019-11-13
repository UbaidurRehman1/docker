#start with a base image containing java runtime
FROM centos

#now installing java (y is for all yes)
RUN yum install -y java

#adding volumes
VOLUME /tmp

#now creating app.jar inside the container
ADD /spring-boot-web-0.0.1-SNAPSHOT.jar app.jar

#updating the created date to current date
RUN sh -c 'touch app.jar'

#entry point for java applications
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]