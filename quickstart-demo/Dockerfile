FROM registry.access.redhat.com/ubi8/openjdk-17 as builder

USER jboss
WORKDIR /tmp/src
COPY --chown=jboss . /tmp/src
RUN mvn package

FROM registry.access.redhat.com/ubi8/openjdk-17
COPY --from=builder /tmp/src/target/*.jar /deployments/app.jar
