FROM maven:3.9 AS BUILD_IMAGE
ENV JAVA_API /javaapi_build
WORKDIR $JAVA_API
COPY ./ $JAVA_API
RUN mvn install -DskipTests

FROM openjdk:8

WORKDIR /javaapi
COPY --from=BUILD_IMAGE /javaapi_build/target/book-work-0.0.1-SNAPSHOT.jar ./book-work-0.0.1.jar

EXPOSE 9000
ENTRYPOINT ["java","-jar","book-work-0.0.1.jar"]
# Test
