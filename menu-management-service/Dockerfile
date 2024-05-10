FROM eclipse-temurin:17-jdk-alpine

COPY target/menu-management-service.jar app.jar

ENV DB_URI="${MONGO_DB_URI}"
ENV ISSUER_URI="${ISSUER_URI}"

EXPOSE 8050

ENTRYPOINT ["java", "-jar", "/app.jar"]