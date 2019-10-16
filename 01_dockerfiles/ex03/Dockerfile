FROM ubuntu

MAINTAINER jronald

RUN apt update && apt upgrade -y
RUN apt install curl openssh-server ca-certificates postfix -y
RUN curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ee/script.deb.sh | bash
RUN apt-get install gitlab-ee

RUN apt update && apt install -y tzdata && \
  apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

EXPOSE 443 80 22

#build - docker build -t ex03 .
# run - docker run -it --rm -p 8080:80 -p 8022:22 -p 8443:443 --privileged ex03

ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && tail -f /dev/null


