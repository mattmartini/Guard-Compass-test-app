source 'https://rubygems.org'

gem 'rails', '3.2.9'

# Bundle edge Rails instead:
# gem 'rails', :git => 'git://github.com/rails/rails.git'

gem 'sqlite3'

gem 'haml-rails'

# Gems used only for assets and not required
# in production environments by default.
group :assets do
  gem 'sass-rails',   '~> 3.2.3'
  gem 'compass-rails'
  gem 'coffee-rails', '~> 3.2.1'

  # See https://github.com/sstephenson/execjs#readme for more supported runtimes
  # gem 'therubyracer', :platforms => :ruby

  gem 'uglifier', '>= 1.0.3'
end

gem 'jquery-rails'

# To use ActiveModel has_secure_password
# gem 'bcrypt-ruby', '~> 3.0.0'

# To use Jbuilder templates for JSON
# gem 'jbuilder'

# Use unicorn as the app server
# gem 'unicorn'

# Deploy with Capistrano
# gem 'capistrano'

# To use debugger
# gem 'debugger'


gem 'rubygems-bundler', :require => false  # gem regenerate_binstubs

group :development, :test do
  gem 'rspec-rails'
  gem 'growl'
  gem 'spork'
end


group :test do
  gem 'factory_girl_rails'
  gem "database_cleaner"
end


group :guard do
  gem 'rb-fsevent',   :require => false if RUBY_PLATFORM =~ /darwin/i # Installs fsevent if on a Mac
  gem 'rb-readline'
  gem 'guard'
  gem 'guard-rails'
  gem 'guard-compass'
  gem 'guard-haml'
  gem 'guard-sass'
  gem 'guard-livereload'
  gem 'guard-spork'
  gem 'guard-rspec'
  gem 'guard-annotate'
end
