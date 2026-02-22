FROM drsjb80/rails-dev
LABEL org.opencontainers.image.authors="beatys@msudenver.edu"
EXPOSE 3000

RUN rails new simple -O
WORKDIR /home/simple
RUN bundle install

CMD ["./bin/rails", "server", "-b", "0.0.0.0"]
