Heroku buildpack: Waveform
=======================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for using [waveform](https://github.com/andrewrk/waveform) in your project.  
It doesn't do anything else, so to actually compile your app you should use [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi) to combine it with a real buildpack.

Usage
-----
To use this buildpack, you should prepare .buildpacks file that contains this buildpack url and your real buildpack url.  

    $ ls
    .buildpacks
    ...
    
    $ cat .buildpacks
    https://github.com/shunjikonishi/heroku-buildpack-waveform
    https://github.com/heroku/heroku-buildpack-play

    $ heroku create --buildpack https://github.com/ddollar/heroku-buildpack-multi

    $ git push heroku master
    ...

You can verify installing ffmpeg by following command.

    $ heroku run "waveform -version"

Hacking
-------
If you want to use your own ffmpeg binary, fork and rewrite following line.

https://github.com/dubsmash/heroku-buildpack-waveform/blob/master/bin/compile#L10
# heroku-buildpack-gifsicle
