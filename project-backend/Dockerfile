FROM ruby:3.0.0

ENV BUNDLE_VERSION 2.2.19
ENV APP /usr/src/app

RUN apt-get update && apt-get install -y netcat && apt-get install -y vim
RUN gem install bundler --version "$BUNDLE_VERSION"

RUN mkdir $APP
WORKDIR $APP

COPY Gemfile* $APP/
COPY . $APP/
RUN bundle install


CMD ["./bin/server-dev"]
