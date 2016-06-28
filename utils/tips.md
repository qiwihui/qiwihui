### configure

When use `jekyll serve` locally to test the blog, you need to install bundle via

    gems install bundler

then, in the root of the project, install needed dependencies through

    bundle install

If you are from China, due to some internet issues as the great firewall has blocked frequently
rubygems.org mirror on Amazon S3, it is a helpless idea to use `https://ruby.taobao.org/` as
gems sources and bundle config.

    $ gem sources --remove https://rubygems.org/
    $ gem sources -a https://ruby.taobao.org/
    $ gem sources -l
    *** CURRENT SOURCES ***

    https://ruby.taobao.org
    # make sure there is only ruby.taobao.org

    $ bundle config mirror.https://rubygems.org https://ruby.taobao.org

For further infomation, visit [RubyGems Mirror - Taobao](https://ruby.taobao.org)