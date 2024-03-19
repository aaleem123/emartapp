FROM openjdk:8 AS Build
WORKDIR /user/src/app
RUN apt update && apt install maven -y 
COPY ./ ./javaapi/
RUN cd javaapi && mvn install -DskipTests 

FROM openjdk:8

COPY --from=Build /user/src/app/target/book-work-0.0.1-SNAPSHOT.jar ./book-work-0.0.1.jar
EXPOSE 9000
ENTRYPOINT [ "java", "-jar", "book-work-0.0.1.jar" ]