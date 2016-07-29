# Gridster::Rails

This is [gridster.js](http://gridster.net) GEMified for the Rails >= 3.1 asset pipeline

[![Gem Version](https://badge.fury.io/rb/gridster-rails.svg)](https://badge.fury.io/rb/gridster-rails)

## Installation

Add this line to your application's Gemfile within the assets group:

    gem 'gridster-rails'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install gridster-rails

## Usage

Add to **application.js**

    //= require jquery.gridster.js

Add to **application.css**

    *= require jquery.gridster.css

Gridster.js
===========

Gridster is a jQuery plugin that makes building intuitive draggable
layouts from elements spanning multiple columns. You can even
dynamically add and remove elements from the grid.

Documentation and usage: [http://gridster.net/](http://gridster.net/).

[Changelog](https://github.com/ducksboard/gridster.js/blob/master/CHANGELOG.md)

License
=======

Distributed under the MIT license.

Whodunit
========

Gridster is maintained by [Ducksboard](http://ducksboard.com/) by Ducksboard occasionally but not actively. @dustmoo and @pushmatrix have also write permissions as Gridster maintainers they are. Thank you guys!

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

How this gem was created
========================

    bundle gem gridster-rails
    cd gridster-rails
    mkdir -p vendor/assets/javascripts
    mkdir -p vendor/assets/stylesheets
    curl https://raw.github.com/ducksboard/gridster.js/master/dist/jquery.gridster.js -o vendor/assets/javascripts/jquery.gridster.js
    curl https://raw.github.com/ducksboard/gridster.js/master/dist/jquery.gridster.css -o vendor/assets/stylesheets/jquery.gridster.css
    echo "" >> README.md; echo "# gridster.js appended README #" >> README.md; echo "" >> README.md
    curl https://raw.github.com/ducksboard/gridster.js/master/README.md >> README.md
    echo "" >> LICENSE; echo "# gridster.js appended LICENSE #" >> LICENSE; echo "" >> LICENSE
    curl https://raw.github.com/ducksboard/gridster.js/master/LICENSE >> LICENSE

modify **lib/gridster-rails/version.rb** to match gridster.js version

    VERSION = "0.5.6"

modify **lib/gridster-rails.rb** to subclass Rails::Engine

    class Engine < ::Rails::Engine
    end

modify **gridster-rails.gemspec**

    gem.description   = "This gem provides jquery.gridster.js and jquery.gridster.css for your Rails 3+ application."
    gem.summary       = "Use gridster with Rails 3+"
    gem.homepage      = "http://rubygems.org/gems/gridster-rails"
    gem.files = Dir["{lib,vendor}/**/*"] + ["LICENSE", "README.md"]
    gem.add_dependency "railties", '>= 3.1.0', '< 6.0'

build

    rake build

release

    rake release