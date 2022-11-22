FROM maven:3.5-jdk-8 AS build  
COPY src /usr/src/app/src  
COPY pom.xml /usr/src/app  
RUN mvn -f /usr/src/app/pom.xml clean package

FROM gcr.io/distroless/java  
COPY --from=build /usr/src/app/target/Calculator-1.0.0.jar /usr/app/Calculator-1.0.0.jar  
ENTRYPOINT ["java","-jar","/usr/app/Calculator-1.0.0.jar"]  
