FROM gradle:jdk17 as build
WORKDIR /home/gradle/src
COPY --chown=gradle:gradle . .
RUN gradle build

FROM openjdk:19-slim
COPY --from=build /home/gradle/src/build/libs/*.jar /app/app.jar
CMD [ "java", "-jar", "/app/app.jar" ]
