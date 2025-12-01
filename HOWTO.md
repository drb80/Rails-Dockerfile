I found the Docker files created by dockerfile-rails wanting. Here are ones
that work for me.

    rails new Todo --minimal
    cd Todo
    rails generate scaffold Item what when:date
    mkdir data

Probably the easiest way to get the two files is

    curl -o Dockerfile https://raw.githubusercontent.com/drb80/Rails-Dockerfile/refs/heads/main/Dockerfile
    curl -o bin/docker-entrypoint https://raw.githubusercontent.com/drb80/Rails-Dockerfile/refs/heads/main/bin/docker-entrypoint

If you want, you can to pull/fetch and this should work:

    git remote add dockerfile https://github.com/drb80/Rails-Dockerfile.git
    git pull dockerfile main

Build using ```docker build -t railstodo .``` for a dev environment, or
```docker build --build-arg RAILS_ENV=production -t railstodo .``` for a
production environment.

Run using ```docker run -it -p 3000:3000 -v ${PWD}/data:/data railstodo```

Note that the SQLite database will be in the data directory after running.
