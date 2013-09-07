Combining HTML Hypermedia APIs and Adaptive Web Design
======================================================

Thoughts, issues and ideas on combining HTML Hypermedia APIs and Adaptive Web Design. Possibly, in the future, also code examples.
Answers to common objections against using HTML as the media type for your API is found here: http://codeartisan.blogspot.se/2012/07/using-html-as-media-type-for-your-api.html


Use two different URLs for web and API
-------
Since you might want to split the solution in the future, more whatever reason, it's good to create such an option right from the start. The simplest way seems to be to have a duplicated DNS entry, pointing to the same IP.

Optimizations
-------
 - strip CSS and script tags for API perspective
 - deal with images (how?). Perhaps client can indicate via the accept header using a prefix/suffix to the media type?


Different flow for humans and machines
-------

My opinion now is it's to much work to separate responses between humans and machines. The "problem" was that the PRG pattern is needed for humans but not for machines. This twitter conversation made me change my mind: https://twitter.com/stilkov/status/335784329449984000
So, use the PRG pattern for both humans and machines - a redirect is interpreted as success and the clint can choose to follow the URL in the redirect or not.

Headless browser support and/or scrapers
------------------------
 - JavaScript: http://phantomjs.org/
 - Ruby: http://mechanize.rubyforge.org/
 - TODO Add more :)

Here is a longer list: https://gist.github.com/evandrix/3694955

However, a headless browser doesn't need to be able to have client JavaScript support in able to use the API.


Client library support for HTML
-----------------------
There are several HTML parser for all possible application platforms out there. I think that parsers with CSS3 syntax (or, think jQuery selector).
Here are some I've found:
 - .NET: https://github.com/jamietre/CsQuery
 - Java: http://jsoup.org/cookbook/extracting-data/selector-syntax
 - iOS: libxml2, see below...
 - Ruby: https://www.engineyard.com/blog/2010/getting-started-with-nokogiri/
 - node: https://github.com/MatthewMueller/cheerio
 - lua: https://github.com/wscherphof/lua-htmlparser

It seems that HTML API support for iOS is lagging behind. You can use libxml2 - good blog post here http://www.cocoawithlove.com/2008/10/using-libxml2-for-parsing-and-xpath.html (found on http://stackoverflow.com/questions/3541615/whats-the-best-approach-for-parsing-xml-screen-scraping-in-ios-uiwebview-or)
The idea of using a UIWebview to access an HTML API actually doesn't seem that bad, if you have implemented the optimization 

Resouces
--------
Blog post: http://www.jayway.com/2012/08/01/combining-html-hypermedia-apis-and-adaptive-web-design/ (lots of links here)
Video of presentation: http://www.youtube.com/watch?v=YCjaOrIhYGg
Slides: http://www.slideshare.net/GustafKotte/html-hypermedia-apis-and-adaptive-web-design-nordic-apis

