# Bootstrap Generators

[![Build Status](https://travis-ci.org/decioferreira/bootstrap-generators.png?branch=master)](https://travis-ci.org/decioferreira/bootstrap-generators)

Bootstrap-generators provides [Twitter Bootstrap](http://getbootstrap.com/) generators for Rails 4 (supported Rails >= 3.1). Bootstrap is a toolkit from Twitter designed to kickstart development of webapps and sites.

## Current Twitter Bootstrap version

The current supported version of Twitter Bootstrap is 3.1.1.

## Installing Gem

In your Gemfile, add this line:

    gem 'bootstrap-generators', '~> 3.1.1'

Or you can install from latest build:

    gem 'bootstrap-generators', :git => 'git://github.com/decioferreira/bootstrap-generators.git'

Run bundle install:

    bundle install

## Generators

Get started:

    rails generate bootstrap:install -f

Once you've done that, any time you generate a controller or scaffold, you'll get [Bootstrap](http://twitter.github.com/bootstrap/) templates.

### Give it a try

    rails generate scaffold post title body:text published:boolean

You can easily customize colors, grid system, fonts, and much more by editing `bootstrap-variables.[less|scss]` on your application assets folder.

## Usage

To print the options and usage run the command `rails generate bootstrap:install --help`

    Usage:
      rails generate bootstrap:install [options]

    Options:
      -e, [--template-engine=TEMPLATE_ENGINE]          # Indicates when to generate template engine
                                                       # Default: erb
      -se, [--stylesheet-engine=STYLESHEET_ENGINE]     # Indicates when to generate stylesheet engine
                                                       # Default: scss
          [--skip-turbolinks], [--no-skip-turbolinks]  # Indicates when to generate skip turbolinks

    Runtime options:
      -f, [--force]                    # Overwrite files that already exist
      -p, [--pretend], [--no-pretend]  # Run but do not make any changes
      -q, [--quiet], [--no-quiet]      # Suppress status output
      -s, [--skip], [--no-skip]        # Skip files that already exist

    Copy BootstrapGenerators default files

### Options

#### Template engines

Supported template engines:

* ERB
* Haml
* Slim

##### Haml

Add the dependency on your Gemfile:

    gem 'haml-rails'

And then run:

    rails generate bootstrap:install --template-engine=haml

##### Slim

Add the dependency on your Gemfile:

    gem 'slim-rails'

And then run:

    rails generate bootstrap:install --template-engine=slim


#### Stylesheet engines

Supported stylesheet engines:

* CSS
* SCSS
* LESS

##### SCSS

Make sure you have `sass-rails` dependency on your Gemfile:

    gem 'sass-rails'

And then run:

    rails generate bootstrap:install --stylesheet-engine=scss

Now you can customize the look and feel of Bootstrap.

##### LESS

Add the dependency on your Gemfile:

    gem 'therubyracer', platforms: :ruby
    gem 'less-rails'

And then run:

    rails generate bootstrap:install --stylesheet-engine=less

Now you can customize the look and feel of Bootstrap.

#### Skip turbolinks

Run the generator with option `--skip-turbolinks` to remove turbolinks references from the generated layout.

## Assets

### Customize and extend Bootstrap

If you select LESS or SCSS as your stylesheet engine, you will get an `app/assets/stylesheets/bootstrap-variables.[less|scss]` file with all of the default variables of Bootstrap. This way you can customize the look and feel of Bootstrap without having to download any extra file.

### Javascript

Select all jQuery plugins (`app/assets/javascripts/bootstrap.js`)

    //= require bootstrap

Or quickly add only the necessary javascript (Transitions: required for any animation; Popovers: requires Tooltips)

    //= require bootstrap/scrollspy
    //= require bootstrap/dropdown
    //= require bootstrap/tab
    //= require bootstrap/button
    //= require bootstrap/collapse
    //= require bootstrap/modal
    //= require bootstrap/carousel
    //= require bootstrap/alert
    //= require bootstrap/transition
    //= require bootstrap/tooltip
    //= require bootstrap/popover
    //= require bootstrap/affix


## Customizing Templates

In Rails 3.0 and above, generators don’t just look in the source root for templates, they also search for templates in other paths. And one of them is lib/templates.

Since Bootstrap Generators installs its templates under lib/templates, you can go and customize them.

## Credits

* [Twitter Bootstrap](http://getbootstrap.com)
