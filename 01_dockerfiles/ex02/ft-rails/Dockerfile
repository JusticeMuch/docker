FROM ruby 

MAINTAINER jronald

RUN apt-get update -y && apt-get install -y build-essential libpq-dev nodejs sqlite3

ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000
ONBUILD RUN bundle install --without production
ONBUILD RUN rails db:migrate
ONBUILD RUN rails server

#build - docker build -t ft-rails:on-build