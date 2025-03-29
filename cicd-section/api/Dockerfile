# ビルド環境
FROM gradle:jdk21 AS build

WORKDIR /app
COPY . /app
RUN ./gradlew build

# アプリ実行環境
FROM openjdk:21
COPY --from=build /app/build/libs/my-app-0.0.1-SNAPSHOT.jar ./my-app.jar
CMD ["java", "-jar", "my-app.jar"]
