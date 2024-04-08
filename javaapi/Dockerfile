FROM openjdk:8 AS Build 
WORKDIR /usr/src/app
RUN apt update && apt install maven -y 
COPY ./ ./javaapi
RUN mvn install _DskipTests 

FROM openjdk:8
COPY --from=Build /usr/src/app/target/book-work-0.0.1-SNAPSHOT.jar ./book-work-0.0.1.jar
EXPOSE 9000 
ENTRYPOINT ["jave", "-jar", "book-work-0.0.1.jar"]
