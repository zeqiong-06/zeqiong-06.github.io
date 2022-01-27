# c0ldstudy.github.io
Personal Blog

#### Local Test Methods

```shell
# update bundle
bundle update
bundle install --path=vendor/bundle

# run jekyll server
jekyll serve
```

If an Apple machine with a M1 chip is used, check the [link](https://colingallagher.me/webdev/2021/04/15/installing-jekyll-apple-m1-mac/) because it is very useful. Especially there is some error with `webrick`.


#### Plugins
- [Github Chart API](https://github.com/2016rshah/githubchart-api)
- [Katex](https://katex.org/docs/browser.html): Being faster than Mathjax but not supporting lots of features.
  - add `kramdown-math-katex` to Gemfile and run `bundle install`
  - Cannot use one `$` to display latex formats
- [MathJax](https://www.mathjax.org/#gettingstarted):
  - Configuration [Tutorial](http://sgeos.github.io/github/jekyll/2016/08/21/adding_mathjax_to_a_jekyll_github_pages_blog.html)
  - There is a [blog](https://www.bersling.com/2016/05/10/displaying-math-on-the-web/) to compare two math engines.
- [jekyll-twitter-plugin](https://github.com/rob-murray/jekyll-twitter-plugin)


#### How to debug in ruby

{{ variable | jsonify }}


if jekyll-paginate is not working, `bundle update; bundle` may be working.

jekyll-paginate-v2 is not woring for some unknow reasons.

Test:
Basically, the following files are required to edited.
- Gemfile: gem 'jekyll-paginate' => gem 'jekyll-paginate-v2'
- _config.yml:
```
gems: [jekyll.-paginate-v2]
pagination:
  enabled: true
  debug: true
  collection: 'posts'
  per_page: 10
  sort_reverse: true
  sort_field: 'date'
  title: ':title'
  trail:
    before: 2
    after: 2
```
[More detail](https://github.com/sverrirs/jekyll-paginate-v2/blob/master/README-GENERATOR.md)

#### Others

1. If the retraction is not unit when being displayed on the web, remove the line break and press return button again in Typro. The key is that the original code is not the same and there have lines between the lines with asterisk.
