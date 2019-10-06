FROM ubuntu

MAINTAINER jronald

RUN apt update && apt upgrade -y
RUN apt install curl openssh-server ca-certificates postfix -y
RUN curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ee/script.deb.sh | bash
RUN apt-get install gitlab-ee


