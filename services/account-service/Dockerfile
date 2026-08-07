# ---------- Stage 1 : Build ----------
FROM maven:3.9.9-eclipse-temurin-17 AS builder

WORKDIR /app

# Copy pom.xml first (better layer caching)
COPY pom.xml .

# Download dependencies
RUN mvn dependency:go-offline

# Copy source code
COPY src ./src

# Build application
RUN mvn clean package

# ---------- Stage 2 : Runtime ----------
FROM eclipse-temurin:17-jre

WORKDIR /app

COPY --from=builder /app/target/java-docker-demo-1.0.0.jar app.jar

ENTRYPOINT ["java","-jar","app.jar"]