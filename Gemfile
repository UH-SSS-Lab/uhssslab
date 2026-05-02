source "https://rubygems.org"

# Modern Jekyll (works with Ruby 3.x and 4.x).
gem "jekyll", "~> 4.3"

group :jekyll_plugins do
  gem "jekyll-feed"
  gem "jekyll-seo-tag"
  gem "jekyll-sitemap"
  gem "jekyll-paginate"
end

# Required for the local serve command.
gem "webrick"

# Windows / JRuby compatibility (no-op on macOS).
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end
