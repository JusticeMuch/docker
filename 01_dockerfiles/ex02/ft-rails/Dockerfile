FROM ruby

MAINTAINER jronald

RUN apt-get update -y && apt-get install -y build essential libpq-dev node-js sqlite3

ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000
ONBUILD RUN bundle install
ONBUILD RUN rake db:create
ONBUILD RUN rake db:migrate