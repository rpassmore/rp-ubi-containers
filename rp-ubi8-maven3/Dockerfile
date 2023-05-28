FROM rp-jdk8:0.0.1

USER root
        # Install packages defined in the 'jboss.container.maven' module
RUN microdnf --setopt=install_weak_deps=0 --setopt=tsflags=nodocs install -y maven-openjdk8 \
    && microdnf clean all \
    && rpm -q maven-openjdk8

ENV MAVEN_VERSION="3.6"

USER default