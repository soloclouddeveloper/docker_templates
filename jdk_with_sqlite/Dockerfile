FROM alpine:3.14

RUN wget -O /etc/apk/keys/adoptium.rsa.pub https://packages.adoptium.net/artifactory/api/security/keypair/public/repositories/apk
RUN echo 'https://packages.adoptium.net/artifactory/apk/alpine/main' >> /etc/apk/repositories
RUN apk add temurin-21-jdk
RUN apk add sqlite

ENV JAVA_HOME /usr/lib/jvm/java-21-temurin
RUN export JAVA_HOME
ENV PATH="${JAVA_HOME}/bin:${PATH}"

CMD ["/bin/sh"]