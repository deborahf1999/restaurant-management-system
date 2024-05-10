FROM eclipse-temurin:17-jdk-alpine

COPY target/menu-management-service.jar app.jar

EXPOSE 8050

ENTRYPOINT ["java", "-jar", "/app.jar"]

# Multi-stage build for a slimmer runtime image
FROM alpine AS runtime

RUN --mount=type=secret,id=DB_URI \
  cat /run/secrets/DB_URI

RUN --mount=type=secret,id=ISSUER_URI \
  cat /run/secrets/ISSUER_URI