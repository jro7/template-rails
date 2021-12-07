# Template to start a new Rails 7 (rc1) project
I wanted a relatively quick way to start a new Ruby on Rails project, without the need to setup my local machine with all the correct versions of Ruby & gems.

The rails new command installs Rails with support for Postgresql, Tailwind CSS and esbuild.

Heavily inspired by https://github.com/pskarlas/rails_fast_dev as starting point.

Main addition was editing in Gitpod.

# Usage
1. clone repository or click on [Use this template](https://github.com/jro7/template-rails/generate)
1. edit new repository in Gitpod (ie. https://gitpod.io/#https://github.com/<your_username>/<your_repository>)
  - Gitpod automatically recognizes the Dockerfile and does a bundle install, if the following command fails, run `bundle install` first
1. run `bundle exec rails new . --javascript esbuild --css tailwind --database postgresql -T`
  - You can choose to answer yes/all to "overwrite the following file(s)", since it's in git ;). But don't forget you will need to add the gitpod setting below


# Start
Run `bin/dev` to start rails
# Edit and preview on Gitpod
It's possible to run the app on gitpod, add the following to `./config/environment/development.rb`, on top of the file after the line `Rails.application.configure do`

```ruby
  # Preview on Gitpod
  config.hosts << ENV["APP_DOMAIN"] unless ENV["APP_DOMAIN"].nil?
  if (gitpod_workspace_url = ENV["GITPOD_WORKSPACE_URL"])
    config.hosts << /.*#{URI.parse(gitpod_workspace_url).host}/
  end

```
