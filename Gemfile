source "https://rubygems.org"

# Jekyll proper, not the `github-pages` gem.
#
# `github-pages` hard-pins Jekyll to 3.9.x, which in turn pins ancient
# activesupport/i18n/kramdown and breaks on any Ruby >= 3.4 (stdlib gems like
# `csv` stopped being default gems). Building with real Jekyll lets this site
# track current Ruby and current Jekyll instead of GitHub's frozen 2021 set.
#
# NOTE: this means the site must be built and deployed by our own CI, not by
# GitHub's legacy branch-based Pages build. See .github/workflows/.
gem "jekyll", "~> 4.4"

group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.17"
end

# `jekyll serve` needs webrick; not a default gem since Ruby 3.0.
gem "webrick", "~> 1.9"

# Windows/JRuby lack zoneinfo files.
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end
