FROM maven:latest as builder
WORKDIR /app
COPY . .
RUN mvn clean install -DskipTests
FROM openjdk:8-jre
WORKDIR /app
COPY --from=builder /app/target/stockmanager-0.0.1-SNAPSHOT.jar .
EXPOSE 8050
CMD ["java", "-jar", "stockmanager-0.0.1-SNAPSHOT.jar"]