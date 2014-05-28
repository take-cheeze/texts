## IRC
* [Protocol(RFC)](http://tools.ietf.org/html/rfc1459.html)
* [Web interface of freenode.](http://webchat.freenode.net/)

## HTTP
* [HTTP2 tests](https://github.com/http2/http2-test)

## [Mutlicast DNS](http://www.multicastdns.org/)
* Zero configuration DNS by Apple.
* Avahi on non-Apple platform.

## AirPlay
* Uses Remove Audio Access Protocol(RAOP) to transfer audio.
* [RAOP protocol detail.](https://xmms2.org/wiki/Technical_note_to_describe_the_Remote_Audio_Access_Protocol_(RAOP)_as_used_in_Apple_iTunes_to_stream_music_to_the_Airport_Express_(ApEx).)

## ShareMouse UDP port
<blockquote>All ShareMouse programs communicate through UDP port 1046 with each other. This setting must be the same on all ShareMouse installations.</blockquote>
* [from the document](http://www.keyboard-and-mouse-sharing.com/docs/09/manual.php#firewall)
* So the port must be set to 1046 on OS X with firewall enabled

## WireShark
* packet capturing software
* can read dumped packets
* [chmod to read packets in OS X](http://blog.nominet.org.uk/tech/2008/04/30/wireshark-capture-under-mac-os-x/)
* [decrypting SSL/TLS traffic](http://support.citrix.com/article/CTX116872)
* [capturing iOS SSL packets](http://blog.rocaz.net/2011/01/1123.html)
  * requires jailbreak
  * [using Burp Proxy](http://blog.rocaz.net/2011/02/1167.html)
* [decrypting https traffic](http://qiita.com/items/baddcf6988ec1f6ac014)

## Capturing iOS device packets
* [setting](http://hycro.crz.jp/wordpress/?p=56)
* use ''rvictl'' command
* UDID can be acquired with Xcode organizer
* target device must be connected with USB cable
* when you disconnected capturing device it will automatically stop.
* to start: `rvictl -s [UDID]`
* to stop: `rvictl -x [UDID]`
