# Gridster::Rails

This is [gridster.js](http://gridster.net) GEMified for the Rails >= 3.1 asset pipeline through the following:

	bundle gem gridster-rails
	cd gridster-rails
	mkdir -p vendor/assets/javascripts
	mkdir -p vendor/assets/stylesheets
	curl https://raw.github.com/dustmoo/gridster.js/master/dist/jquery.gridster.js -o vendor/assets/javascripts/jquery.gridster.js
	curl https://raw.github.com/dustmoo/gridster.js/master/dist/jquery.gridster.css -o vendor/assets/stylesheets/jquery.gridster.css
	echo "" >> README.md; echo "# gridster.js appended README #" >> README.md; echo "" >> README.md
	curl https://raw.github.com/dustmoo/gridster.js/master/README.md >> README.md
	echo "" >> LICENSE; echo "# gridster.js appended LICENSE #" >> LICENSE; echo "" >> LICENSE
	curl https://raw.github.com/dustmoo/gridster.js/master/LICENSE >> LICENSE
	git add .
	git commit -am "initial gridster-rails"
	git remote add origin git@github.com:vanetten/gridster-rails.git

* modify **lib/gridster-rails/version.rb** to match gridster.js version

		VERSION = "0.1.5"

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

	//= require jquery.gridster.js

Add to **application.css**

	*= require jquery.gridster.css

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

Public Service Announcement from Dustin Moore (dustmoo)
=======================================================

Gridster is not currently being actively maintained by 
[Ducksboard](http://ducksboard.com/).

I and others have been given access to the repo to help
 maintain and address issues.

I have created a fork of gridster that supports more advanced
 features, like widget-swapping and static widgets.

It can be found here: https://github.com/dustmoo/gridster.js

Currently the code-base is different and I don't have time to
reconcile the fork with this repo. 

If anyone would like to help me improve my fork and reconcile 
it with the main library I would be happy for the help.


License
=======

Distributed under the MIT license.

Whodunit
========

Gridster is built by [Ducksboard](http://ducksboard.com/).

dustmoo Modifications
===========

Changelog 2013-04-3

Fork now handles standard behavior properly with swap allowing larger widgets to shift down.

Changelog 2013-04-2

Added Demo to Repository.

Changelog 2013-02-27

Added "Static widget support" Static Items default to the "static" class.

You can customize this class by using the code below:

	$.gridster({
		static_class: 'custom_class',
		draggable: {
            items: ".gs_w:not(.custom_class)"
        }
	});

I have also added functions creating a much more thourough check of whether the player can occupy the space you are moving it too.
This version is much more reliable in swapping space with widgets.

There are also new options for Maximum Rows and Maximum Columns:
	
	$.gridster({
		max_rows: map_rows,
    	max_cols: map_cols,
    	shift_larger_widgets_down: false
    });

Setting the maximum amount of rows only completely works if you disable shifting larger widgets down at the moment. 


Changelog 2012-11-26

Reworked swapping functionality to better handle large to small widget handling.

---

Widgets of smaller or equal size to the dragged widget (player) 
will swap places with the original widget. 

This causes tiles to swap left and right as well as up and down.

By default smaller players will shift larger widgets down.

I have added an option to prevent this behavior:

	$.gridster({
		shift_larger_widgets_down: false
	});

By setting shift_larger_widgets_down to false, smaller widgets will not displace larger ones.



