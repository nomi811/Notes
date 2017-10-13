# <a name="top">Rails</a>

### [Commands](#commands)
### [Database](#database)



### <a name="commands">Commands</a> :point_up:[top](#top)

`$gem install rails --no-ri --no-doc --version 4.0.0` - to not install all the docs

`$rails new <app_name> -d postgresql -T` - this sets up a new rails app using postgresql as the database and doesn't set up the test files.
`$rails g controller demo index`

### <a name="database">Database</a> :point_up:[top](#top)

`$rake routes` - shows all available routes

`$bundle exec rake db:migrate` - try if `$rake db:migrate` doesn't work

`$rake db:schema:dump` - tell Rails to connect to the schema and export our database


:point_up:[top](#top)
