FROM openjdk:8

WORKDIR /app

COPY PingPong.java /app

RUN javac PingPong.java

EXPOSE 8001

CMD ["java", "PingPong"]

