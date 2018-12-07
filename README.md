# Inventorious

An inventory management and tracking system built with Ruby on Rails 5.

!["Dashboard"](https://github.com/zmitzie/inventorious/blob/master/dashboard_screenshot.png "Dashboard")

Demo: [https://#/](https://inventorious.herokuapp.com/)

## Description

Gestion Inventaire Ruby on rails

## Installation Instructions

### Install Rails

- Make sure you have a Ruby version > 2.2.2 installed in your system
- Install [RubyGems](https://rubygems.org/pages/download)
- run `gem install rails -v 5.0.2`

### Download Repo

- Download this repo, and unzip it
- `cd inventorious` to cd into the folder
- `bundle`
- `rails db:migrate db:seed`

### Set Enviroment Variables

You need to set 6 enviroment variables, for emails to be delivered (for ActionMailer, password reset, etc).

You can use [the Figaro Gem](https://github.com/laserlemon/figaro) if you like.

| Enviroment Variable Names |                                             Are                                             |
| ------------------------- | :-----------------------------------------------------------------------------------------: |
| EMAIL_DOMAIN              |                                 Domain of your email server                                 |
| EMAIL_USERNAME            |                 Username for your email (most of the time name@domain.tld)                  |
| EMAIL_PASSWORD            |                                   Password for your email                                   |
| SMTP_SERVER               |                                Address for your smtp server                                 |
| EMAIL_SEND_FROM           |                         Email address where email will go out from                          |
| ACTION_MAILER_SEND_TO     | Email address which will receive email notifications on order create, cancel, renew, return |

You may have to further configure the SMTP delivery options. If so, edit this file `config/environments/development.rb`

If you are deploying to Heroku, set `HEROKU_URL` as the url of your app!

### Run the server

- Run `rails s` to start the server
- Without stoping the server, open another terminal window and run `rake jobs:work` (needed in order for ActionMailer to work and deliver emails)
- Visit http://localhost:3000
- Use `demo@demo.com` `change_me` for the email and password. Change the password and email once you login. Create more users via the Console.
