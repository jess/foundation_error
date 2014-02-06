Example vaniella app to show foundation error:

```
jessmbp.local ruby 2.1.0p0 ~/projects $ chruby
   ruby-1.8.7-p374
   ruby-1.9.3-p448
   ruby-2.0.0-p353
 * ruby-2.1.0
jessmbp.local ruby 2.1.0p0 ~/projects $ rails -v
Rails 4.0.2
jessmbp.local ruby 2.1.0p0 ~/projects $ rails new foundation_error

...

# add foundation-rails to gem file
jessmbp.local ruby 2.1.0p0 ~/projects/foundation_error $ bundle
jessmbp.local ruby 2.1.0p0 ~/projects/foundation_error $ bundle show
foundation-rails
/Users/jess/.gem/ruby/2.1.0/gems/foundation-rails-5.1.0.0

# works find on initial boot
jessmbp.local ruby 2.1.0p0 ~/projects/foundation_error $ rails s
=> Booting WEBrick
=> Rails 4.0.2 application starting in development on
http://0.0.0.0:3000
=> Run `rails server -h` for more startup options
=> Ctrl-C to shutdown server

...

# install foundation
jessmbp.local ruby 2.1.0p0 ~/projects/foundation_error $ rails g
foundation:install
      insert  app/assets/javascripts/application.js
      append  app/assets/javascripts/application.js
      create  app/assets/stylesheets/foundation_and_overrides.scss
      append  app/assets/stylesheets/foundation_and_overrides.scss
      insert  app/assets/stylesheets/application.css
    conflict  app/views/layouts/application.html.erb
Overwrite
/Users/jess/projects/foundation_error/app/views/layouts/application.html.erb?
(enter "h" for help) [Ynaqdh] Y
       force  app/views/layouts/application.html.erb

# setup a real view

# config/routes
root 'application#root'

# app/views/application/root.html.erb
testing


Started GET "/" for 127.0.0.1 at 2014-02-06 07:27:21 -0500
Processing by ApplicationController#root as HTML
  Rendered application/root.html.erb within layouts/application (0.1ms)
Completed 500 Internal Server Error in 644ms

ActionView::Template::Error (File to import not found or unreadable: foundation/components/range-slider.
Load paths:
  /Users/jess/projects/foundation_error/app/assets/images
  /Users/jess/projects/foundation_error/app/assets/javascripts
  /Users/jess/projects/foundation_error/app/assets/stylesheets
  /Users/jess/projects/foundation_error/vendor/assets/javascripts
  /Users/jess/projects/foundation_error/vendor/assets/stylesheets
  /Users/jess/.gem/ruby/2.1.0/gems/turbolinks-2.2.1/lib/assets/javascripts
  /Users/jess/.gem/ruby/2.1.0/gems/jquery-rails-3.1.0/vendor/assets/javascripts
  /Users/jess/.gem/ruby/2.1.0/gems/coffee-rails-4.0.1/lib/assets/javascripts
  /Users/jess/.gem/ruby/2.1.0/gems/foundation-rails-5.1.0.0/vendor/assets/javascripts
  /Users/jess/.gem/ruby/2.1.0/gems/foundation-rails-5.1.0.0/vendor/assets/stylesheets
  (in /Users/jess/projects/foundation_error/app/assets/stylesheets/foundation_and_overrides.scss:28)):
     6:
     7:     <title><%= content_for?(:title) ? yield(:title) : "foundation-rails" %></title>
     8:
     9:     <%= stylesheet_link_tag    "application" %>
    10:     <%= javascript_include_tag "vendor/modernizr" %>
    11:     <%= csrf_meta_tags %>
    12:   </head>
  app/assets/stylesheets/foundation_and_overrides.scss:7
  app/views/layouts/application.html.erb:9:in `_app_views_layouts_application_html_erb__4462749592775865875_70367224003820'

```


