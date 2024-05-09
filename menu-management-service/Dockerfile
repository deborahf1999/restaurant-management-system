FROM eclipse-temurin:17-jdk-alpine

WORKDIR /menu-management-service

COPY target/menu-management-service.jar app.jar

WORKDIR ../

RUN --mount=type=secret,id=DB_URI \
    sed -i "s/DB_URI=/DB_URI=$(cat /run/secrets/MONGO_DB_URI)/" .env.production

RUN --mount=type=secret,id=ISSUER_URI \
    sed -i "s/ISSUER_URI=/ISSUER_URI=$(cat /run/secrets/ISSUER_URI)/" .env.production \

EXPOSE 8050

ENTRYPOINT ["java", "-jar", "/app.jar"]