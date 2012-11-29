# Guardfile
# More info at https://github.com/guard/guard#readme

### Rails
guard 'rails', :port => 3000 do
  watch('Gemfile.lock')
  watch(%r{^(config|lib)/.*})
end


### Compass 
guard 'compass' do
  watch(%r{^(app|lib|vendor)/assets/stylesheets/(.*)\.s[ac]ss})
  #watch(%r{(app/assets/stylesheets/.+\.s[ac]ss)})
end


### HAML
guard 'haml' do
  watch(%r{/^.+(\.html\.haml)/})
end


### SASS
# With asset pipline sass guard not needed, this just notifies of change
guard 'sass', :input => 'app/assets/stylesheets', :noop => true, :hide_success => true, #:compass => true


### Livereload
guard 'livereload' do
  watch(%r{app/.+\.(erb|haml)})
  watch(%r{app/views/.+\.(erb|haml|slim)$})
  watch(%r{app/helpers/.+\.rb})
  watch(%r{(public/|app/assets).+\.(css|js|html)})
  watch(%r{(app/assets/.+\.css)\.s[ac]ss}) { |m| m[1] }
  watch(%r{(app/assets/.+\.js)\.coffee}) { |m| m[1] }
  watch(%r{config/locales/.+\.yml})
  watch(%r{(app/assets/stylesheets/.+\.css)\.s[ac]ss}) { |m| m[1] }
  watch(%r{(app/assets/stylesheets/.+\.s[ac]ss)}) { |m| m[1] }
  watch(%r{(app/assets/javascripts/.+\.js)\.coffee}) { |m| m[1] }
  watch(%r{(app/assets/javascripts/.+\.js)}) { |m| m[1] }
  # Rails Assets Pipeline
  watch(%r{(app|vendor)/assets/\w+/(.+\.(css|js|html)).*})  { |m| "/assets/#{m[2]}" }
end


### Spork
guard 'spork', :cucumber_env => { 'RAILS_ENV' => 'test' }, :rspec_env => { 'RAILS_ENV' => 'test' }, :bundler => false do
  watch('config/application.rb')
  watch('config/environment.rb')
  watch(%r{^config/environments/.+\.rb$})
  watch(%r{^config/initializers/.+\.rb$})
  watch('spec/spec_helper.rb')
  watch(%r{^spec/support/.+\.rb$})
  watch('Gemfile')
  watch('Gemfile.lock')
  watch('spec/spec_helper.rb') { :rspec }
  watch('test/test_helper.rb') { :test_unit }
  watch(%r{features/support/}) { :cucumber }
end


### Rspec
guard 'rspec', :bundler => false, :all_on_start => false, :all_after_pass => false do
  watch(%r{^spec/.+_spec\.rb$})
  watch(%r{^lib/(.+)\.rb$})     { |m| "spec/lib/#{m[1]}_spec.rb" }
  watch('spec/spec_helper.rb')  { "spec" }
  
  # Rails
  watch(%r{^spec/.+_spec\.rb$})
  watch(%r{^app/(.+)\.rb$})                           { |m| "spec/#{m[1]}_spec.rb" }
  watch(%r{^lib/(.+)\.rb$})                           { |m| "spec/lib/#{m[1]}_spec.rb" }
  watch(%r{^app/(.*)(\.erb|\.haml)$})                 { |m| "spec/#{m[1]}#{m[2]}_spec.rb" }
  watch(%r{^app/controllers/(.+)_(controller)\.rb$})  { |m| ["spec/routing/#{m[1]}_routing_spec.rb", "spec/#{m[2]}s/#{m[1]}_#{m[2]}_spec.rb", "spec/acceptance/#{m[1]}_spec.rb"] }
  watch(%r{^spec/support/(.+)\.rb$})                  { "spec" }
  watch('spec/spec_helper.rb')                        { "spec" }
  watch('config/routes.rb')                           { "spec/routing" }
  watch('app/controllers/application_controller.rb')  { "spec/controllers" }
  # Capybara request specs
  watch(%r{^app/views/(.+)/.*\.(erb|haml)$})          { |m| "spec/requests/#{m[1]}_spec.rb" }
end


### Annotate
guard 'annotate' do
  watch( 'db/schema.rb' )

  # Uncomment the following line if you also want to run annotate anytime
  # a model file changes
  #watch( 'app/models/**/*.rb' )

  # Uncomment the following line if you are running routes annotation
  # with the ":routes => true" option
  #watch( 'config/routes.rb' )
end


