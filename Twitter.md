# API
* [Document](https://dev.twitter.com/docs/api|Document)
## v1.0
* v1.1が出たので古いAPI扱い
* API制限の割り振りが割と自由
* v1.0はいつまで使えるの？
  * [2013/03/05まで](https://dev.twitter.com/docs/faq#10647)
  * ６カ月の猶予がある．

## v1.1
* [list rate limit eased](http://api.techmood.jp/2013/02/22/128)
* rss, xml廃止, jsonのみ
* API制限の割り振りが，全体が増加した代わりに不自由
  * lists/statusesも15req/win
* [API制限概要](https://dev.twitter.com/docs/rate-limiting/1.1)
* [具体的なAPI制限](https://dev.twitter.com/docs/rate-limiting/1.1/limits)
* 15分を1windowとして，1windowごとにAPI制限がリセットされる．
* 残りAPI数がレスポンスに含まれるようになった．
* ストリーミングAPIの充実が図られた．
  * リスト代わりに使える？
  * statuses/filter
    * follow: 5000アカウントまで
    * track: 400語まで
    * location: 25個の0.1～360度の区画
    * パラメータが巨大になる場合はPOSTを使うべし
  * user
    * trackも独立して使える
  * site
    * ユーザの集合を追尾するAPI
    * followは初期値で100, add_userで100ずつ，最大1000個まで可能
    * [https://dev.twitter.com/docs/streaming-apis/streams/site]
    * [https://dev.twitter.com/docs/streaming-apis/streams/site/control]

## v1.1対応計画
* lists/membersを15分ごとに15回requestして，idを収集
* リスト全部15個おきにstatuses/filterコネクションを作成
* ライブラリは [[https://github.com/ttezel/twit]] を使う
* タイムラインと検索(saved_searches/list)は，userで済ませる．
* tweetだけのRSS出力にも対応する？
  * URLはjqueryとかでreplaceする
  * function(tweet) {
    * tweet.urls.forEach(function(url) {
      * tweet.text.replace(url,
        * $('<div />').append($('<a />').attr('href', url)).html());
    * }
    * return tweet;
  * }
* followとtrackは配列にしてjoinすればいい
* Twit.streamでのイベント
  * tweet
  * delete
  * limit
  * scrub_geo