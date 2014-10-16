* [KoRec](http://www.arugoworks.net/korec)
 * First goal for the app.

## Supporting services.

### Live services.
Most use rtmp streams.
* [超A&G](http://www.agqr.jp/)
  * [agqr.rb](https://gist.github.com/ybenjo/9904543)
* [radiko](http://radiko.jp/)
  * [ripdiko](https://github.com/miyagawa/ripdiko)
* [ListenRadio](http://listenradio.jp/)
  * Uses AdobeHDS.
* [らじる★らじる](http://www3.nhk.or.jp/netradio/)
  * [ripdiru](https://github.com/harupong/ripdiru)

### Non-live services.
* [Lantisネットラジオ](http://lantis-net.com/)
* [音泉](http://www.onsen.ag/)
* [HiBiKi Radio Station](http://hibiki-radio.jp/)
  * Should support today's talk.
* [Animate TV](http://www.animate.tv/radio/)
  * Has WMV version.

## Fetching data.
* [rtmpdump](https://rtmpdump.mplayerhq.hu/)
  * Use it in rtmp source.
* [glued](https://github.com/simongregory/glued)
  * Use it in Adobe HTTP Dynamic Streaming.
  * See [AdobeHDS.php](https://github.com/K-S-V/Scripts/blob/master/AdobeHDS.php) for live streaming.
* Use HTTP module for general media file downloading.
* Fetching should be done in other thread or process.
* [ruby-librtmp](https://github.com/plainprogrammer/ruby-librtmp)
  * Ruby librtmp binding.

## Fetching program table.
* Korec should be a good example.
* [超A&G program table](http://www.agqr.jp/timetable/digital-mf.php)
  * Guest information needs to be fetched from `#guestinfo` of [root page](http://www.agqr.jp/index.php).

## Encoding downloaded files.
* Use [ffmpeg](https://www.ffmpeg.org/).
* flv or mp3s should be always encoded to m4a or m4v.

## Saving encoded files.
* File name should contain service, program name(or channel), count.
* Wants support of transfering to iTunes or Podcast.

## Implementing app.
* 
