# encoding: utf-8
$:.push File.expand_path("../lib", __FILE__)

require 'bundler'
require 'bundler/setup'
require 'ridley-connectors'

class Default < Thor

  require 'thor/rake_compat'

  include Thor::RakeCompat
  Bundler::GemHelper.install_tasks

  desc "build", "Build ridley-connectors-#{Ridley::Connectors::VERSION}.gem into the pkg directory"
  def build
    Rake::Task["build"].execute
  end

  desc "install", "Build and install ridley-connectors-#{Ridley::Connectors::VERSION}.gem into system gems"
  def install
    Rake::Task["install"].execute
  end

  desc "release", "Create tag v#{Ridley::Connectors::VERSION} and build and push ridley-connectors-#{Ridley::Connectors::VERSION}.gem to Rubygems"
  def release
    Rake::Task["release"].execute
  end

  class Spec < Thor
    namespace :spec
    default_task :all

    desc "all", "run all tests"
    def all
      exec "rspec --color --format=documentation spec"
    end
  end
end
