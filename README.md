This is is a copy of [tenex/rails-assets](https://github.com/tenex/rails-assets) with our improvement.

> [Bundler](http://bundler.io) to [Bower](http://bower.io) proxy

This README concerns the development aspect of the project. **[Visit the site](https://rails-assets.org) to learn how to use Rails Assets in your application.**

## Development

### Setup

```sh
git clone git@github.com:tenex/rails-assets.git && cd rails-assets
bundle install && npm install
cp config/database{.sample,}.yml
cp config/application{.sample,}.yml
# edit config/database.yml and config/application.yml if necessary.
bin/rake db:setup
foreman start
```

### Convert Bower package into Ruby gem using CLI

```sh
bin/rake 'component:convert[jquery,2.0.3]'
```

This will create `rails-assets-NAME-VERSION.gem` file.

You can remove this component by:

```sh
bin/rake 'component:destroy[jquery,2.0.3]'
```


## Gems with a .js in their name

For packages from bower that have a .js in their name like [typeahead.js](https://github.com/twitter/typeahead.js) which can generate a gem with the name rails-assets-typehead.js if You want to use this gem with Rails 4.2 or higher in order for your gem to work in your application.js you have to require it as follow

```
//= require typeahead.js.js
```

instead of

```
//= require typeahead.js
```

