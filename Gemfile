# A sample Gemfile
source "https://rubygems.org"

# gem "rails"
gem "jekyll"
gem "deep_merge"

# For easy publishing to github pages
require 'json'
require 'open-uri'
versions = JSON.parse(open('https://pages.github.com/versions.json').read)

gem 'github-pages', versions['github-pages']
