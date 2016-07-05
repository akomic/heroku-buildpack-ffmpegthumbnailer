Heroku buildpack: FFMpeg
=======================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for using [ffmpegthumbnailer](https://code.google.com/p/ffmpegthumbnailer) in your project.  
It doesn't do anything else, so to actually compile your app you should use [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi) to combine it with a real buildpack.

Usage
-----
To use this buildpack, you should prepare .buildpacks file that contains this buildpack url and your real buildpack url.  

    $ ls
    .buildpacks
    ...
    
    $ cat .buildpacks
    https://github.com/heroku/heroku-buildpack-python.git
    https://github.com/akomic/heroku-buildpack-ffmpeg.git
    https://github.com/akomic/heroku-buildpack-ffmpegthumbnailer.git

    $ heroku create --buildpack https://github.com/ddollar/heroku-buildpack-multi.git

    $ git push heroku master
    ...

You can verify installation of ffmpegthumbnailer by issuing the following command.

    $ heroku run "ffmpegthumbnailer -version"
