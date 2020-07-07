FROM ruby:2.7
RUN apt-get update -qq && apt-get install -y nodejs postgresql-client
# Ruby2.7の変更によってWarningが出るのを消しておく
ENV RUBYOPT='-W:no-deprecated -W:no-experimental'
RUN mkdir /app
WORKDIR /app
COPY Gemfile /app/Gemfile
COPY Gemfile.lock /app/Gemfile.lock
RUN bundle install
COPY . /app

# Add a script to be executed every time the container starts.
COPY entrypoint.sh /usr/bin/
RUN chmod +x /usr/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]
EXPOSE 3000

# Start the main process.
CMD ["rails", "server", "-b", "0.0.0.0"]
