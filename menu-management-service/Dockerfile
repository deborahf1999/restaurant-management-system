FROM alpine

# Install Java
RUN apk update && apk add --no-cache openjdk17-jdk

COPY target/menu-management-service.jar app.jar

EXPOSE 8050

ENTRYPOINT ["java", "-jar", "/app.jar"]