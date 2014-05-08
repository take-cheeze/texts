* Platform as a Service

# [.profile.d scripts](https://devcenter.heroku.com/articles/profiled)
* config file to specify stable env variable such as $PATH
* scripts execute order isn't defined so scripts must be independent from it
* node.js buildpack use this to specify PATH to node_modules executable scripts
* $BUILD_DIR /.profile.d
* $HOME will be the slug path

# [maintenance mode](https://devcenter.heroku.com/articles/maintenance-mode)
* used to disable app temporary

# Buildpack
* [list of official buildpack](https://devcenter.heroku.com/articles/buildpacks)
* [list of 3rd party buildpack](https://devcenter.heroku.com/articles/third-party-buildpacks)
* [API spec](https://devcenter.heroku.com/articles/buildpack-api)
  * detect
  * compile
  * release
* [node.js buildpack](https://github.com/heroku/heroku-buildpack-nodejs)
  * uses compiled node.js executable
* [mruby buildpack using compiled mruby binary](http://www.sitepoint.com/hacking-mruby-onto-heroku/)
* [C build pack using '''make''' in compile](https://github.com/atris/heroku-buildpack-C)