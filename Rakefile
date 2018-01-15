require 'html-proofer'
require 'yaml'

###### Show tasks by default - equivalent to `rake -T`
# A task must have a description in order to be shown

Rake::TaskManager.record_task_metadata = true

task :default do
  Rake::application.options.show_tasks = :tasks  # this solves sidewaysmilk problem
  Rake::application.options.show_task_pattern = //
  Rake::application.display_tasks_and_comments
end


###### Actual tasks

desc 'Build the jekyll site'
task :build do
  sh "bundle exec jekyll build"
end

desc 'Build and serve the jekyll site'
task :serve do
  sh "bundle exec jekyll serve -H 0.0.0.0"
end

desc 'Build and test the jekyll site'
task :test => :build do
  # Test depends on build task
  options = { :assume_extension => true }
  HTMLProofer.check_directory("./_site", options).run
end
