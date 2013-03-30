---
layout: entry
title: Rails development environment with rbenv+ruby-build+bundler
---

Make sure that you removed rvm, becouse rbenv conflicts with rvm:

{% highlight bash %}
$ rm -rf ~/.rvm ~/.rvmrc
{% endhighlight %}

Install rbenv+ruby-build

{% highlight bash %}
$ brew install rbenv ruby-build
{% endhighlight %}

Install ruby
List of available rubys available through `rbenv install --list`

{% highlight bash %}
$ brew install openssl && CONFIGURE_OPTS="--with-openssl-dir=`brew --prefix openssl`" && rbenv install 2.0.0-dev
{% endhighlight %}

Set installed ruby globally

{% highlight bash %}
$ rbenv global 2.0.0-dev
{% endhighlight %}

Install bundler

{% highlight bash %}
$ gem install bundler && rbenv rehash
{% endhighlight %}

**Remember to rerun `rbenv rehash` after installation of gems which have binaries**

Create gemset using bundler

{% highlight bash %}
$ mkdir ror_proj
$ cd ror_proj
$ echo "gem 'rails'" > Gemfile
$ mkdir -p vendor/bundle
$ bundle install --path vendor/bundle
{% endhighlight %}

Create some aliases

{% highlight bash %}
$ echo 'alias bi="bundle install --path vendor/bundle"' >> ~/.bash_profile
$ echo 'alias begem="bundle exec gem"'  >> ~/.bash_profile
$ echo 'alias berake="bundle exec rake"' >> ~/.bash_profile
$ echo 'alias berails="bundle exec rails"' >> ~/.bash_profile
$ echo 'alias becap="bundle exec cap"'  >> ~/.bash_profile
{% endhighlight %}

Create rails app

{% highlight bash %}
$ cd .. && berails ror_proj --gemfile=ror_proj/Gemfile
{% endhighlight %}

Start created app

{% highlight bash %}
$ cd ror_proj && berails server
{% endhighlight %}