# Heroku cheatsheet

Heroku is a cloud platform that lets companies build, deliver, monitor and scale apps — we're the fastest way to go from idea to URL, bypassing all those infrastructure headaches.

## Create an application

```
heroku create *app_name*

git push heroku master
```

## CLI reference

Primary help topics, type "heroku help TOPIC" for more details:

  addons    #  manage add-on resources
  apps      #  manage apps (create, destroy)
  auth      #  authentication (login, logout)
  config    #  manage app config vars
  domains   #  manage domains
  logs      #  display logs for an app
  ps        #  manage dynos (dynos, workers)
  releases  #  manage app releases
  run       #  run one-off commands (console, rake)

Additional topics:

  access         #  CLI to manage access in Heroku Applications
  buildpacks     #  manage the buildpack for an app
  certs          #  manage ssl endpoints for an app
  drains         #  list all log drains
  features       #  manage optional features
  git            #  manage local git repository for app
  help           #  list commands and display help
  keys           #  manage authentication keys
  labs           #  manage optional features
  local          #  run heroku app locally
  login          #  login with your Heroku credentials.
  maintenance    #  manage maintenance mode for an app
  members        #  manage membership in organization accounts
  notifications  #  display notifications
  orgs           #  manage organization accounts
  pg             #
  pgbackups      #  manage backups of heroku postgresql databases
  pipelines      #  manage collections of apps in pipelines
  plugins        #  manage plugins to the heroku gem
  redis          #  manage heroku redis instances
  regions        #  list available regions
  spaces         #  manage heroku private spaces
  stack          #  manage the stack for an app
  status         #  status of the Heroku platform
  update         #  update the heroku client
  version        #  display version

  ## Links

  * https://www.heroku.com
