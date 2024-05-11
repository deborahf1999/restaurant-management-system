FROM alpine

# Install Java
RUN apk update && apk add --no-cache openjdk17-jdk

RUN --mount=type=secret,id=DB_URI \
  cat /run/secrets/DB_URI

RUN --mount=type=secret,id=ISSUER_URI \
  cat /run/secrets/ISSUER_URI \

COPY target/menu-management-service.jar app.jar

EXPOSE 8050

ENTRYPOINT ["java", "-jar", "/app.jar"]