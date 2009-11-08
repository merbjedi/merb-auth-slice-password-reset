require 'rubygems'
require 'rake/gempackagetask'
require 'spec/rake/spectask'
require 'merb-core'
require 'merb-core/tasks/merb'
require 'merb-core/test/tasks/spectasks'

GEM_NAME = "merb-auth-slice-password-reset"
AUTHOR = "Daniel Neighman, Christian Kebekus"
EMAIL = "has.sox@gmail.com"
HOMEPAGE = "http://merbivore.com/"
SUMMARY = "Password reset for Merb Auth"
DESCRIPTION = "Merb Slice that adds basic password-reset functionality to merb-auth-based merb applications."
GEM_VERSION = "0.9.14"

spec = Gem::Specification.new do |s|
  s.rubyforge_project = 'merb'
  s.name = GEM_NAME
  s.version = GEM_VERSION
  s.platform = Gem::Platform::RUBY
  s.has_rdoc = true
  s.extra_rdoc_files = ["README.textile", "LICENSE", 'TODO']
  s.summary = SUMMARY
  s.description = DESCRIPTION
  s.author = AUTHOR
  s.email = EMAIL
  s.homepage = HOMEPAGE
  s.add_dependency('merb-slices', '>= 1.0.0')
  s.add_dependency('merb-auth-core', ">= 1.0.0")
  s.add_dependency('merb-auth-more', ">= 1.0.0")
  s.add_dependency('merb-mailer', ">= 1.0.0")
  s.require_path = 'lib'
  s.files = %w(LICENSE README.textile Rakefile TODO) + Dir.glob("{lib,spec,app,public,stubs}/**/*")
end

Rake::GemPackageTask.new(spec) do |pkg|
  pkg.gem_spec = spec
end

desc "Install the gem"
task :install do
  Merb::RakeHelper.install(GEM_NAME, :version => GEM_VERSION)
end

desc "Uninstall the gem"
task :uninstall do
  Merb::RakeHelper.uninstall(GEM_NAME, :version => GEM_VERSION)
end

desc "Create a gemspec file"
task :gemspec do
  File.open("#{GEM_NAME}.gemspec", "w") do |file|
    file.puts spec.to_ruby
  end
end

desc 'Default: run spec examples'
task :default => 'spec'
