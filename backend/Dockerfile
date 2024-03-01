FROM adoptopenjdk/maven-openjdk11 AS build
WORKDIR /app 
COPY . .
RUN mvn clean package -DskipTests

FROM adoptopenjdk/openjdk11
WORKDIR /app
COPY --from=build /app/target/*.jar ./my-backend.jar
CMD ["java", "-jar", "my-backend.jar"]