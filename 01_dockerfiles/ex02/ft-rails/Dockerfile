FROM ruby

MAINTAINER jronald

RUN apt-get update -y && apt-get install -y build-essential libpq-dev nodejs sqlite3
RUN gem install bundler:2.0.2

ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000
ONBUILD RUN bundle install
ONBUILD RUN rake db:create
ONBUILD RUN rake db:migrate

#build - docker build -t ft-rails:on-build .