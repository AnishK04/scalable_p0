# Stage 1
FROM maven:3.6.3-jdk-11 AS build
WORKDIR /app
COPY codebase/* .
RUN mvn package

# Stage 2
FROM maven:3.6.3-jdk-11 AS production
WORKDIR /app
COPY --from=build /app/* .
#RUN ["chmod", "+x", "target/ums-1.0.jar"]
CMD ["java", "-jar", "/app/target/ums-1.0.jar"]

