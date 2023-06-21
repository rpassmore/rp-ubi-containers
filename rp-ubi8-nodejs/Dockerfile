#FROM registry.access.redhat.com/ubi9-minimal
FROM ghcr.io/rpassmore/rp-ubi-containers/rp-ubi8-base:v0.0.2

ENV NODEJS_VERSION=18

RUN microdnf -y module enable nodejs:$NODEJS_VERSION && \
    #MODULE_DEPS="make gcc gcc-c++ " && \
    MODULE_DEPS="" && \
    INSTALL_PKGS="$MODULE_DEPS nodejs npm " && \
#    ln -s /usr/lib/node_modules/nodemon/bin/nodemon.js /usr/bin/nodemon && \
    microdnf install -y --setopt=tsflags=nodocs $INSTALL_PKGS && \
    microdnf -y clean all --enablerepo='*'
    
