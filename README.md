# Heroku Buildpack: AutoMigrate

This heroku buildpack automatically runs your Rails migrations. In order to use it,
just create a `.buildpacks` file in your application with this content

```bash
https://github.com/heroku/heroku-buildpack-ruby.git
https://github.com/Arkham/heroku-buildpack-automigrate.git
```

Then commit it and push to heroku.

```bash
git commit -m "Added AutoMigrate" && git push heroku master
```

Now everytime you push to heroku, your migrations will be run :)

## Features

AutoMigrate will run the migrations only when you actually add new ones to
your project. In order to do this, it saves the list of the existing migrations
in a cache folder. If you need to purge the cache at any time, use
[heroku-repo](https://github.com/heroku/heroku-repo).

## Advantages

This approach of running migrations yields the following benefits:

* No need for maintanance mode
* No need to fork heroku buildpacks and mantain them
* No need to restart the application after running migrations
* The extra step is run only when there are actually new migrations

## Credits

Most of this code has been shamelessly stolen from
[heroku-buildpack-smartmigrate](https://github.com/hammady/heroku-buildpack-smartmigrate)
