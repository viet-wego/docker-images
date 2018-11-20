FROM jenkins/jnlp-slave
LABEL maintainer="tdviet12@gmail.com"

ENV CLOUDSDK_CORE_DISABLE_PROMPTS 1
ENV PATH /opt/google-cloud-sdk/bin:$PATH

USER root

RUN apt-get update -y \
    && apt-get install -y jq libapparmor-dev libseccomp-dev libltdl-dev \
    && rm -rf /var/lib/apt/lists/*
RUN curl https://sdk.cloud.google.com | bash && mv google-cloud-sdk /opt
RUN gcloud components install kubectl

# create k8s config directory
RUN mkdir -p /opt/jenkins/.kube
ENV KUBECONFIG /opt/jenkins/.kube/config
