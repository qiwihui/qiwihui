qiwihui.com
=============

After trying many blog sites, I finally settled in Github Pages, no database nor rich text editor. 
Just as simple as it can when writing the markdown posts. This site is about my thoughts and writings
in programming(mainly in python and golang), mathematics and something about my life.

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

### Contact me:

You can reach me by dropping me a mail or open a PR against this project. Anyway, a tweet is welcome.

* Email: qiwihui@qiwihui.com
* Twitter: @upchaos

### License

All the meterials without special comments, will be published under [Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh). And I think it is really an excellent idea.
