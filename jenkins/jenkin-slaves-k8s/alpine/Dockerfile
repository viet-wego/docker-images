FROM jenkins/jnlp-slave:3.29-1-alpine
LABEL maintainer="tdviet12@gmail.com"

ENV CLOUDSDK_CORE_DISABLE_PROMPTS 1
ENV PATH /opt/google-cloud-sdk/bin:$PATH

USER root

RUN apk update \
    && apk add bash jq python py-pip curl docker \
    && apk add libapparmor-dev --repository=http://dl-cdn.alpinelinux.org/alpine/edge/testing \
    && apk add libltdl --repository=http://dl-cdn.alpinelinux.org/alpine/edge/main \
    && rm -rf /var/lib/apt/lists/*
RUN curl https://sdk.cloud.google.com | bash && mv google-cloud-sdk /opt
RUN gcloud components install kubectl

# create k8s config directory
RUN mkdir -p /opt/jenkins/.kube
ENV KUBECONFIG /opt/jenkins/.kube/config