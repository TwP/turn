task :default => :test

desc "Run unit tests"
task :test do
  ruby "-Ilib bin/turn -Ilib test/*.rb"
end

desc "build gem package"
task :gem => ['.ruby'] do
  sh 'gem build .gemspec'
  sh 'mv *.gem pkg/'
end

file '.ruby' => ['Profile', 'lib/turn/version.rb'] do
  sh 'dotruby source Profile'
end

# Might be useful one day, so we'll leave it here.
#
# Rake::TaskManager.class_eval do
#   def remove_task(task_name)
#     @tasks.delete(task_name.to_s)
#   end
# end
#
# def remove_task(task_name)
#   Rake.application.remove_task(task_name)
# end

# EOF
