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

desc 'Generate members/<member>.md files from _data/members.yml'
task :build_members do
  # Gather all users in _data/members.yml
  # and create a <user>.md for each one.
  # Also:
  # - Create the members directory if not found
  # - Create a README.md file with a warning
  #
  members_dir = 'miembros'
  if ! Dir.exist?(members_dir) then
    Dir.mkdir(members_dir)
    puts "Created #{members_dir}/"
  end
  
  readme_file = "#{members_dir}/README.md"
  readme_msg = "#WARNING\nAll the contents in this folder were generated automatically.\n\nDo not change manually anything.\n\nCheck the `Rakefile` task `build_members` for more info."
  if ! File.exist?(readme_file) then
    File.write(readme_file, readme_msg)
    puts "Created #{readme_file}"
  end
  
  users = []
  members = YAML.load_file('_data/members.yml')
  members['teams'].each { |team| users += team['authors'] }
  users += members['teachers']
  users.each { |user|
    user_file = "#{members_dir}/#{user}.md"
    if ! File.exist?(user_file) then
      content = "---\nlayout: user_profile\nauthor: #{user}\n---"
      File.write(user_file, content)
      puts "Created #{user_file}"
    end
  }
end
