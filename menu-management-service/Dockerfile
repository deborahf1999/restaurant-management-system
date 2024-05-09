FROM eclipse-temurin:17-jdk-alpine

RUN mvn clean install

COPY target/menu-management-service.jar app.jar

RUN --mount=type=secret,id=DB_URI \
    sed -i "s/DB_URI=/DB_URI=$(cat /run/secrets/MONGO_DB_URI)/" .env.production

RUN --mount=type=secret,id=ISSUER_URI \
    sed -i "s/ISSUER_URI=/ISSUER_URI=$(cat /run/secrets/ISSUER_URI)/" .env.production

RUN pwd

EXPOSE 8050

ENTRYPOINT ["java", "-jar", "/app.jar"]