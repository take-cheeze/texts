# Outline
* A web service to convert pages that is for PC browsers to make it readable in mobile devices.
* It is useful to remove unnecessary part of a pages.
* In Chrome AdBlock can remove Ads and tags you don't want too.

# Readability
* 'http://www.readability.com/m?url=' + encodeURIComponent(url)
* title: #rdb-article-content
* body: #rdb-article-body
* [Algorithm?](http://code.google.com/p/arc90labs-readability/source/browse/trunk/js/readability.js)
* [source code](https://code.google.com/p/arc90labs-readability/)

# Instapaper
* 'http://www.instapaper.com/m?u=' + encodeURIComponent(url)
* title: $('h1')[0].text()
* body: #story


# ViewText
* 'http://viewtext.org/article?url=['](http://www.google.com/gwt/x?u=') + encodeURIComponent(url)
# Google Mobilizer
* 'http://www.google.com/gwt/x?u=' + encodeURIComponent(url)
* title: $('title').text()
* body: $('body')

# Poponta Proxy
* mobilizer for iOS
* service is over