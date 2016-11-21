Spree Sample:
by Jerry Pascua ([6hoursdaily](https://twitter.com/6hoursdaily))

## MACHINE SETUP
  * Ubuntu 16.04 setup

        sudo apt-get update
        sudo apt-get install imagemagick nodejs rbenv

  * OSX setup

        brew update
        brew install imagemagick nodejs rbenv

  then setup rbenv as per usual instructions.

  * Setup ruby 2.3.1

        rbenv install 2.3.1
        gem install bundler

## DEVELOPMENT SETUP
  Clone and setup repo

    git clone git@github.com:6hoursdaily/spree-sample.git
    cd spree-sample
    bundle install

  Add this to your `~/.gitconfig` file

    [branch]
      autosetuprebase = always

  Keep your `remotes` references clean

    git fetch -p

  Setup ENV vars

    echo ‘SECRET_KEY_BASE=ChangeMe_4325465f7tu’ >> .env
    echo SECRET_TOKEN=ChangeMe_tdxyfughkjly’ >> .env
    echo DEVISE_SECRET_KEY=ChangeMe_uit64eytd’ >> .env

  Setup Spree migrations and seed

    bundle exec rake railties:install:migrations
    bundle exec rake db:migrate
    bundle exec rake db:seed
    bundle exec rake spree_sample:load

  Start application

    rails s -p 3001

## TEST IN BROWSER
http://localhost:3001

http://localhost:3001/admin 
  * spree@example.com / spree123
