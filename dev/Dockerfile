FROM ubuntu:18.04
ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get update && \
    apt-get install maven git -y
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git /tmp/boxfuse/
WORKDIR /tmp/boxfuse/
RUN mvn package
WORKDIR /usr/local/tomcat/webapp
RUN cp /tmp/boxfuse/target/hello-1.0.war .
