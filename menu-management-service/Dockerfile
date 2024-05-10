FROM eclipse-temurin:17-jdk-alpine

COPY target/menu-management-service.jar app.jar

EXPOSE 8050

ENTRYPOINT ["java", "-jar", "/app.jar"]

# Multi-stage build for a slimmer runtime image
FROM alpine AS runtime

RUN echo $DB_URI
RUN echo $ISSUER_URI

ENTRYPOINT ["java", "-jar", "/app.jar"]