require 'rspec/core/rake_task'
require 'rubocop/rake_task'

desc 'Run tests'
RSpec::Core::RakeTask.new(:spec)

desc 'Run Rubocop on the gem'
RuboCop::RakeTask.new(:rubocop) do |task|
  task.patterns = ['spec/**/*.rb']
  task.fail_on_error = true
end

desc 'Build the site'
task :build do
  fail unless system 'jekyll build'
end

task default: [:spec, :rubocop, :build]
