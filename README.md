Zehua Ma's personal website. Powered by <a href="http://jekyllrb.com/" target="_blank">Jekyll</a> with <a href="https://github.com/alshedivat/al-folio">al-folio</a> and <a href="https://github.com/jindongwang/jindongwang.github.io">jindongwang</a> theme.

#### Local setup using Docker
Similar to <a href="https://github.com/alshedivat/al-folio">al-folio</a>, this webpage could be easily setup with local docker image:
```bash
$ docker-compose -f docker-local.yml up
```

#### Local Setup
Assuming you have [Ruby](https://www.ruby-lang.org/en/downloads/) and [Bundler](https://bundler.io/) installed on your system, first [fork](https://guides.github.com/activities/forking/) the theme to `github.com:<your-username>/<your-repo-name>` and do the following:

```bash
$ git clone git@github.com:<your-username>/<your-repo-name>.git
$ cd <your-repo-name>
$ gem install rmagick
$ bundle install
$ bundle exec jekyll serve
```
Noted that `rmagick` is needed because of different `jekyll_plugins` settings compared to [al-folio](https://github.com/alshedivat/al-folio).

#### Deployment
As stated in [CLAMS](https://checlams.github.io/blog/2022/deploytutorial/) and many issues, the error `Unknown tag 'bibliography'` inevitably occurs in automatic deployment, due to the conflict between the security setting of Github and `plugins: jekyll/scholar`.

It seems that manual deployment is the only solution:
```bash
$ ./bin/deploy
```
Use the `master` branch for the source code and deploys the webpage to `gh-pages`.