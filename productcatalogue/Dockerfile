FROM maven:latest as builder
WORKDIR /app
COPY . .
RUN mvn clean install -DskipTests
FROM openjdk:8-jre
WORKDIR /app
COPY --from=builder /app/target/productcatalogue-0.0.1-SNAPSHOT.jar .
EXPOSE 8020
CMD ["java", "-jar", "productcatalogue-0.0.1-SNAPSHOT.jar"]