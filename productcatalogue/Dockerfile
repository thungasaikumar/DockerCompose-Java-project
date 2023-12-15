#used maven latest image and named as builder for docker to recognise as BUILDER
FROM maven:latest as builder
# created app directory
WORKDIR /app
# copied the code in app
COPY . .
# to clean the previous artifact and create new and to skip te test cases inside the code
RUN mvn clean install -DskipTests
# using jre to run the jar/application of version 8
FROM openjdk:8-jre
WORKDIR /app
# we should use the from=builder to copy the jar in target otherwise it wont get the jar and copy into app
COPY --from=builder /app/target/productcatalogue-0.0.1-SNAPSHOT.jar .

EXPOSE 8020
#mentioned java to run the java application/ produced jar file.
CMD ["java", "-jar", "productcatalogue-0.0.1-SNAPSHOT.jar"]