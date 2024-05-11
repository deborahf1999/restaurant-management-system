FROM eclipse-temurin:17-jdk-alpine

COPY target/menu-management-service.jar app.jar

# Copy the Dockerfile-secrets
COPY dockerfile-secrets /tmp/dockerfile-secrets

# Build a new stage to inject secrets
FROM debian:latest

COPY --from=0 /tmp/dockerfile-secrets .

# Execute the Dockerfile-secrets to inject environment variables
RUN sh dockerfile-secrets

EXPOSE 8050

ENTRYPOINT ["java", "-jar", "/app.jar"]
