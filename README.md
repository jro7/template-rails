# Template to start a new Rails 7 (alfa) project

Heavily inspired by https://github.com/pskarlas/rails_fast_dev as starting point.

Main addition was editing in Gitpod

# Usage
1. clone repository
1. edit new repository in Gitpod
1. run `bundle exec rails new . --javascript esbuild --css tailwind --database postgresql -T`



# Edit and preview on Gitpod
It's possible to run the app on gitpod, add the following to `./config/environment/development.rb`, on top of the file after the line `Rails.application.configure do`

```ruby
  # Preview on Gitpod
  config.hosts << ENV["APP_DOMAIN"] unless ENV["APP_DOMAIN"].nil?
  if (gitpod_workspace_url = ENV["GITPOD_WORKSPACE_URL"])
    config.hosts << /.*#{URI.parse(gitpod_workspace_url).host}/
  end

```
