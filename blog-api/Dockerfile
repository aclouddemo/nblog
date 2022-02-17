FROM registry.cn-beijing.aliyuncs.com/hub-mirrors/maven:3-jdk-8 AS build  
COPY src /usr/src/app/src  
COPY pom.xml /usr/src/app  
COPY settings.xml /user/src/app/settings.xml
RUN mvn -f /usr/src/app/pom.xml -s /user/src/app/settings.xml clean package -DskipTests

FROM registry.cn-beijing.aliyuncs.com/hub-mirrors/openjdk:8-jdk-alpine
VOLUME /tmp
ARG JAR_FILE=target/blog-api-0.0.1.jar
COPY --from=build /usr/src/app/${JAR_FILE} app.jar
RUN mkdir -p /upload/
RUN wget http://arms-apm-shanghai.oss-cn-shanghai.aliyuncs.com/ArmsAgent.zip -O ArmsAgent.zip
RUN unzip ArmsAgent.zip -d ./
ENTRYPOINT ["java","-javaagent:/ArmsAgent/arms-bootstrap-1.7.0-SNAPSHOT.jar","-Darms.licenseKey=","-Darms.appName=blog-api ","-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]