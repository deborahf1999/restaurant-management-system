FROM eclipse-temurin:17-jdk-alpine

RUN --mount=type=secret,id=MONGO_DB_URI cat /run/secrets/MONGO_DB_URI \
  --mount=type=secret,id=ISSUER_URI cat /run/secrets/ISSUER_URI

COPY target/menu-management-service.jar app.jar

EXPOSE 8050

ENTRYPOINT ["java", "-jar", "/app.jar"]