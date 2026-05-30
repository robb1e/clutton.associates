source "https://rubygems.org"

gem "jekyll", "~> 4.3"

# WEBrick is no longer part of the Ruby standard library (Ruby 3.0+),
# but `jekyll serve` needs it for the local dev server.
gem "webrick", "~> 1.8"

group :jekyll_plugins do
  gem "jekyll-sitemap"
end

# Windows and JRuby do not include zoneinfo files, so bundle the tzinfo-data gem
# and associated library.
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

# Performance booster for watching directories on Windows.
gem "wdm", "~> 0.1.1", :platforms => [:mingw, :x64_mingw, :mswin]
