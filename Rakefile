require 'rake'
require 'bundler'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gemspec|
    gemspec.name = "chargify_api_ares"
    gemspec.summary = "A Chargify API wrapper for Ruby using ActiveResource"
    gemspec.description = ""
    gemspec.email = "mklett@grasshopper.com"
    gemspec.homepage = "http://github.com/grasshopperlabs/chargify_api_ares"
    gemspec.authors = ["Michael Klett", "The Lab Rats @ Phase Two Labs", "Brian Rose","Nathan Verni"]
    
    bundle = Bundler::Definition.from_gemfile('Gemfile')
    bundle.dependencies.each do |dep|
      next unless dep.groups.include?(:runtime)
      gemspec.add_dependency(dep.name, dep.requirement.to_s)
    end
    
    Jeweler::GemcutterTasks.new
  end
rescue LoadError
  puts "Jeweler not available. Install it with: sudo gem install jeweler"
end

require 'spec/rake/spectask'
Spec::Rake::SpecTask.new(:spec) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.spec_files = FileList['spec/**/*_spec.rb']
end

Spec::Rake::SpecTask.new(:rcov) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rcov = true
end

task :default => :spec