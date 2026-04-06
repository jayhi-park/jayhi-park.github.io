FROM ruby:3.3-slim

RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    git \
 && rm -rf /var/lib/apt/lists/*

RUN gem install bundler --no-document

WORKDIR /site

COPY Gemfile ./
RUN bundle install

EXPOSE 4000 35729
