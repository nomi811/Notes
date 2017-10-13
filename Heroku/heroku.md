# <a name="top">Heroku</a>

### Making a website live on Heroku

`$heroku login`
`$heroku create` to create the app with a random Heroku name
`$git push heroku master` to push changes to Heroku

`$heroku git:remote -a <app_name>` - to create heroku remote

`$heroku open` to open the app in the browser

`$heroku run rake db:migrate` - to run the production (heroku) database

`$heroku ps` - to see if app is up and running
`$heroku releases` - to see if they match GitHub
`$heroku run bash` - to look at heroku files

`$rake assets:recompile RAILS_ENV=production` - to compile assets again
`$bundle exec rake assets:precompile` - to compile assets again

:point_up:[top](#top)
