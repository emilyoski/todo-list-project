require "rake/testtask"
require "bundler/gem_tasks"
require "find"

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

desc 'Find file names in project'
task :list_filenames do
  Find.find(Dir.pwd) do |path|
    next if path.include?('/.')
    puts File.basename(path) if File.file?(path)
  end
end