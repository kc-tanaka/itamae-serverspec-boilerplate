require 'rake'
require 'rspec/core/rake_task'


targets = []

task :serverspec    => 'serverspec:all'
task :default => :serverspec

namespace :serverspec do

  task :all     => targets
  task :default => :all

  targets.each do |target|
    desc "Run serverspec tests to #{target}"
    RSpec::Core::RakeTask.new(target.to_sym) do |t|
      ENV['TARGET_HOST'] = target
      t.pattern = "spec/*_spec.rb"
      t.varbose = false
    end
  end
end
