# You can change this base image to anything else
# But make sure to use the correct version of Java
# You can change this base image to anything else
# But make sure to use the correct version of Java
FROM adoptopenjdk/openjdk11:alpine-jre

# Simply the artifact path
ARG artifact=target/spring-boot-web.jar

WORKDIR /opt/app

COPY ${artifact} app.jar

# Add a Jenkins user with UID 1000
RUN addgroup -g 1000 jenkins && adduser -D -u 1000 -G jenkins jenkins

# Change ownership of the application directory to the Jenkins user
RUN chown -R jenkins:jenkins /opt/app

# This should not be changed
ENTRYPOINT ["java","-jar","app.jar"]

