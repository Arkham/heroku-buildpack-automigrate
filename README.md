# Heroku Buildpack: Automigrate

This heroku buildpack automatically runs your Rails migrations. In order to use it,
create a `.buildpacks` file in your application

```bash
https://github.com/heroku/heroku-buildpack-ruby.git
https://github.com/Arkham/heroku-buildpack-automigrate.git
```

Then commit it and push to heroku.

```bash
git commit -m "Added automigrate" && git push heroku master
```

Now everytime you push to heroku, your migrations will be run :)
