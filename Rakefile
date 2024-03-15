require "bundler/gem_tasks" # optional: adds common rake tasks
require "rake/testtask" # optional: builds list of tests automatically
require 'find' # needed for the specific 'Print file' tasks below

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

desc 'Print files'
task :print_files do
  Find.find('.') do |path|
    puts path unless (path.include?('/.') || !File.file?(path))
  end
end
# Add a task to your Rakefile that lists every file in your project except those
#  whose names begin with . and those that reside in a directory whose name begins
#   with ..

# You can use Find::find from the Ruby standard library. 
# You will also need File#file? to test whether a name in Find#find's 
# block is a file or a directory.