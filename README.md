Heroku buildpack: Echoprint Codegen
=======================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for using [echoprint codegen](https://github.com/echonest/echoprint-codegen) in your project.  
It doesn't do anything else, so to actually compile your app you should use [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi) to combine it with a real buildpack.

Usage
-----
To use this buildpack, you should prepare .buildpacks file that contains this buildpack url and your real buildpack url.  

    $ ls
    .buildpacks
    ...
    
    $ cat .buildpacks
    https://github.com/shunjikonishi/heroku-buildpack-ffmpeg
    https://github.com/mrrad/heroku-buildpack-taglib
    https://github.com/mrrad/heroku-buildpack-echoprint-codegen
    https://github.com/heroku/heroku-buildpack-ruby

    $ heroku create --buildpack https://github.com/ddollar/heroku-buildpack-multi

    $ git push heroku master
    ...

You can verify installing ffmpeg by following command.

    $ heroku run "echoprint-codegen"

