#FROM registry.gitlab.com/rpassmore/rp-ubi-containers/rp-ubi8-jdk8:0.0.1
FROM  ghcr.io/rpassmore/rp-ubi-containers/rp-ubi8-jdk8:v0.0.1

ARG MAVEN_VERSION=3.6.3
ARG BASE_URL=https://archive.apache.org/dist/maven/maven-3/${MAVEN_VERSION}/binaries/

USER root
        # Install packages defined in the 'jboss.container.maven' module
RUN microdnf --setopt=install_weak_deps=0 --setopt=tsflags=nodocs --disableplugin=subscription-manager install -y tar-1.30-9.el8.x86_64 gzip-1.9-13.el8_5.x86_64 \
   && microdnf clean all


RUN mkdir -p /usr/share/maven /usr/share/maven/ref && \
   curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz && \
   tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1 && \
   rm -f /tmp/apache-maven.tar.gz   && \
   ln -s /usr/share/maven/bin/mvn /usr/bin/mvn

USER 185
