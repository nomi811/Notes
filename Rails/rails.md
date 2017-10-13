# <a name="top">Rails</a>

### [Commands](#commands)
### [Database](#database)
### [Testing](#testing)



### <a name="commands">Commands</a> :point_up:[top](#top)

`$gem install rails --no-ri --no-doc --version 4.0.0` - to not install all the docs

`$rails new <app_name> -d postgresql -T` - this sets up a new rails app using postgresql as the database and doesn't set up the test files.

`$rails g controller demo index`

`$rails g controller Pages home about contact` (home, about, contact are the actions)

### <a name="database">Database</a> :point_up:[top](#top)

`$rake routes` - shows all available routes

`$bundle exec rake db:migrate` - try if `$rake db:migrate` doesn't work

`$rake db:schema:dump` - tell Rails to connect to the schema and export our database

### <a name="testing">Testing</a> :point_up:[top](#top)

To write tests for website

put `gem "rspec-rails"` in gemfile and run bundle first.

`$rails g rspec:install`

To make `-d postgresql -T` the default configuration when you create a new rails app:
  - create a file in home directory of the computer called `.railsrc`
  - add the line `-d postgresql -T` to the file

  `$rails g rspec:model post`


:point_up:[top](#top)
