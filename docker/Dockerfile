FROM ruby:3.3-slim

RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    git \
 && rm -rf /var/lib/apt/lists/*

RUN gem install jekyll bundler --no-document

WORKDIR /site

COPY Gemfile* ./
RUN bundle install 2>/dev/null || true

EXPOSE 4000

CMD ["bundle", "exec", "jekyll", "serve", "--host", "0.0.0.0", "--livereload"]
