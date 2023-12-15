FROM maven:latest as builder
WORKDIR /app
COPY . .
RUN mvn clean install -DskipTests
FROM openjdk:8-jre
WORKDIR /app
COPY --from=builder /app/target/shopfront-0.0.1-SNAPSHOT.jar .
EXPOSE 8010
CMD ["java", "-jar", "shopfront-0.0.1-SNAPSHOT.jar"]