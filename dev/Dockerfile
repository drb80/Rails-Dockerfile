FROM drsjb80/rails-dev
LABEL org.opencontainers.image.authors="beatys@msudenver.edu"
EXPOSE 3000

WORKDIR /home
COPY . .
RUN bundle install

RUN ./bin/rails db:prepare

EXPOSE 3000
# CMD ["/bin/sh"]
CMD ["./bin/rails", "server", "-b", "0.0.0.0"]
