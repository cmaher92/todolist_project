require 'rake/testtask'
require "bundler/gem_tasks"
require 'find'

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

# Add a task to your Rakefile that lists every file in your project except
# those whose names begin with . and those that reside in a directory
# whose name begins with .

desc "List files in project"
task :list do
  Find.find(ENV['PWD']) do |path|
    basename = File.basename(path)
    Find.prune if FileTest.directory?(path) && basename.start_with?('.')
    puts File.basename(path) unless
         (basename.start_with?('.')|| File.directory?(path))
  end
end
