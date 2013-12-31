require 'rake'
require "bundler/gem_tasks"
require 'rake/testtask'
require 'rspec/core/rake_task'
require 'coveralls/rake/task'
require 'rdoc/task'

task :default => [:test, :spec]

Rake::TestTask.new(:test) do |t|
  t.libs << 'lib'
  t.pattern = 'test/**/*_test.rb'
  t.verbose = true
end

RSpec::Core::RakeTask.new(:spec)

Rake::RDocTask.new(:rdoc) do |rdoc|
  rdoc.rdoc_dir = 'rdoc'
  rdoc.title    = 'Nickel'
  rdoc.options << '--line-numbers' << '--inline-source'
  rdoc.rdoc_files.include('lib/**/*.rb')
end

Coveralls::RakeTask.new
task :test_with_coveralls => [:test, :spec, 'coveralls:push']
