# Gridster::Rails

This is [gridster.js](http://gridster.net) GEMified for the Rails >= 3.1 asset pipeline through the following:

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
	git add .
	git commit -am "initial gridster-rails"
	git remote add origin git@github.com:vanetten/gridster-rails.git

* modify **lib/gridster-rails/version.rb** to match gridster.js version

		VERSION = "0.1.0.1"

* modify **lib/gridster-rails.rb** to subclass Rails::Engine

		class Engine < ::Rails::Engine
		end

* modify **gridster-rails.gemspec**

		gem.description   = "This gem provides jquery.gridster.js and jquery.gridster.css for your Rails 3 application."
		gem.summary       = "Use gridster with Rails 3"
		gem.homepage      = "http://rubygems.org/gems/gridster-rails"
		gem.files = Dir["{lib,vendor}/**/*"] + ["LICENSE", "README.md"]
		gem.add_dependency "railties", "~> 3.1"

* build

		rake build

* release

		rake release

## Installation

Add this line to your application's Gemfile within the assets group:

    gem 'gridster-rails'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install gridster-rails

## Usage

Add to **application.js**

	//= require jquery.gridster.js`

Add to **application.css**

	*= require fullcalendar`

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

# gridster.js appended README #

Gridster.js
===========

Gridster is a jQuery plugin that makes building intuitive draggable
layouts from elements spanning multiple columns. You can even
dynamically add and remove elements from the grid.

More at [http://gridster.net/](http://gridster.net/).

License
=======

Distributed under the MIT license.

Whodunit
========

Gridster is built by [Ducksboard](http://ducksboard.com/).
