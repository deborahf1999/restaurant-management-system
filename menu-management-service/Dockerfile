FROM alpine

# Install Java
RUN apk update && apk add --no-cache openjdk17-jdk

COPY target/menu-management-service.jar app.jar

RUN --mount=type=secret,id=DB_URI \
  cat /run/secrets/DB_URI

RUN --mount=type=secret,id=ISSUER_URI \
  cat /run/secrets/ISSUER_URI \

EXPOSE 8050

ENTRYPOINT ["java", "-jar", "/app.jar"]