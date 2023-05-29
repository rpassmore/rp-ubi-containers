#FROM registry.gitlab.com/rpassmore/rp-ubi-containers/rp-ubi8-base:0.0.1
FROM  ghcr.io/rpassmore/rp-ubi-containers/rp-ubi8-base:main

USER root

RUN microdnf --setopt=install_weak_deps=0 --setopt=tsflags=nodocs install -y java-1.8.0-openjdk-devel \
            && microdnf clean all \
            && rpm -q java-1.8.0-openjdk-devel

ENV \
  JAVA_HOME="/usr/lib/jvm/java-1.8.0" \
  JAVA_VENDOR="openjdk" \
  JAVA_VERSION="1.8.0" 


USER 185
