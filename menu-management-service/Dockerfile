FROM eclipse-temurin:17-jdk-alpine

COPY target/menu-management-service.jar app.jar

RUN --mount=type=secret,id=MONGO_DB_URI\
  cat /run/secrets/MONGO_DB_URI \

RUN --mount=type=secret,id=ISSUER_URI\
  cat /run/secrets/ISSUER_URI\

EXPOSE 8050

ENTRYPOINT ["java", "-jar", "/app.jar"]