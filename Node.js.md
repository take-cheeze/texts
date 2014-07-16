* Asynchronous API based web server framework
* [Repository](https://github.com/joyent/node)
* [version available in Heroku](https://devcenter.heroku.com/articles/nodejs-versions)

## GC
* [explicit GC](http://koexuka.blogspot.jp/2012/07/nodejsgc.html)
  * pass --expose_gc
  * call global.gc();

## [Hubot](http://hubot.github.com/)
* bot framework by GitHub
* written in CoffeeScript
* [repository](https://github.com/github/hubot)
* [using hubot](http://d.hatena.ne.jp/anatoo/20120204/1328368042)
* [using hubot in heroku](http://naoty.hatenablog.com/entry/2012/12/30/034105)
* [IRC](http://blog.fumiz.me/2012/07/27/hubot-irc-bot-easy/)
* [twitter adapter](https://github.com/MathildeLemee/hubot-twitter)
* [slides about hubot](http://www.slideshare.net/kazufumiotani/hubotbot)
* [logger](https://github.com/adragomir/hubot-logger)
  * only supports IRC
  * creates another express server

### [IRC Adapter](https://github.com/nandub/hubot-irc)
* [how to configure](https://github.com/github/hubot/wiki/Adapter:-IRC)
* use HUBOT_IRC_UNFLOOD if you want the bot to have interval between posts.

### Scripts
* [examples](http://blog.fumiz.me/2012/08/05/hubot-irc-bot-script/)
* [hubot script writing manual](http://theprogrammingbutler.com/blog/archives/2011/10/28/hubot-scripts-explained/)
* [Official ones](https://github.com/github/hubot-scripts)
  * load from this if you specify hubot-scripts.json
* scripts located in scripts/ is automatically loaded.
* [hubot-scripts catalog](http://hubot-script-catalog.herokuapp.com/)
  * list of how to use.

## Feed
* [feed generator](http://projets.jpmonette.net/en/feed)
  * [repository](https://github.com/jpmonette/feed)
  * supports atom and rss generation
* [feed-parser](https://github.com/danmactough/node-feedparser)

## [linkify](https://github.com/thejh/node-linkify)
* module to linkify url in the text
* supports html and latex mode

## Document
* [One page reference](http://nodejs.org/api/all.html)
* [Module lists](https://github.com/joyent/node/wiki/Modules)

## Google Reader
* [google reader api example](http://h5y1m141.hatenablog.com/entry/20101126/p1)
* [google reader api example 2](http://h5y1m141.hatenablog.com/entry/20101102/p1)
* [unofficial document](https://code.google.com/p/pyrfeed/wiki/GoogleReaderAPI)
* [Google Client Login](https://github.com/Ajnasz/GoogleClientLogin)
* [googlereaderauth](https://github.com/Tobbe/googlereaderauth)

## Qt
* Qt bindings in node.js
* [Repository](https://github.com/arturadib/node-qt)
* [Using node-qt](http://d.hatena.ne.jp/ishikawam/20120410/p1)

## Database
* [LevelDB bindings](https://github.com/my8bird/node-leveldb)

## API binding
* [Twit](https://github.com/ttezel/twit)
  * Twitter API Binding that supports streaming API

## Scraping
* [jsdom](https://github.com/tmpvar/jsdom)
  * Pure javascript DOM implemetation.
* [node-jquery](https://github.com/coolaj86/node-jquery)
* [html compressor](https://code.google.com/p/htmlcompressor/)
  * can be used to reduce transferring data size.

## NPM
* Package manager for node
* [Repository](https://github.com/isaacs/npm)
* [Home Page](https://npmjs.org/)
* To use it create package.json in the root directory of repository.

## Express
* [Repository](https://github.com/visionmedia/express)
* [Reference](http://expressjs.com/api.html)
* [Connect](http://www.senchalabs.org/connect/)
  * Middle ware used in express.
  * Add support of compression.
* [Using session in express.](http://blog.modulus.io/nodejs-and-express-sessions)
  * Use cookie parser and express.session.

## Request Module
* [Repository](https://github.com/mikeal/request)
* Well used module for http requests.
* Less bugs.
* [URL expanding](http://www.2ality.com/2012/04/expand-urls.html)
