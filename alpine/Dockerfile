FROM adoptopenjdk/openjdk11:jdk-11.0.1.13-alpine-slim

RUN apk add --virtual .build-dependencies wget && \
    mkdir -p /opt/gradle && \
    cd /opt/gradle && \
    wget --quiet https://services.gradle.org/distributions/gradle-5.0-bin.zip && \
    unzip -qd /opt/gradle /opt/gradle/gradle-5.0-bin.zip && \
    apk del .build-dependencies && \
    rm -rf /opt/gradle/gradle-5.0-bin.zip && \
    echo 'export PATH=$PATH:/opt/gradle/gradle-5.0/bin' > /etc/profile.d/gradle.sh && \
    source /etc/profile.d/gradle.sh && \
    java --version && \
    gradle --version
