require 'rubygems'
require 'rake'
require 'rdoc'
require 'date'
require 'yaml'
require 'tmpdir'
require 'jekyll'

desc "Generate blog files"
  task :generate do
    Jekyll::Site.new(Jekyll.configuration({
      "source"      => ".",
      "destination" => "_site"
    })).process
  end


desc "Generate and publish blog to gh-pages"
  task :publish => [:generate] do
    Dir.mktmpdir do |tmp|
      system "mv _site/* #{tmp}"
      system "git branch -D master"
      system "git checkout -b master"
      system "rm -rf *"
      system "mv #{tmp}/* ."
      message = "Site updated at #{Time.now}"
      system "git add ."
      system "git commit -am #{message.shellescape}"
      system "git push origin --all --force"
      system "git checkout source"
    end
  end

task :default => :publish
