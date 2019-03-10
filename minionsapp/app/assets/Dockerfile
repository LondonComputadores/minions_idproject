FROM ruby:2.5-alpine

RUN apk update && apk add build-base nodejs postgresql-dev

RUN mkdir /minionsapp
WORKDIR /minionsapp

COPY Gemfile Gemfile.lock ./
RUN bundle install --binstubs

COPY . .

LABEL maintainer="Nick Janetakis <ahlexpaes.itsolutions@gmail.com>"

CMD puma -C config/puma.rb
