Combining HTML Hypermedia APIs and Adaptive Web Design
======================================================

Thoughts, issues and ideas on combining HTML Hypermedia APIs and Adaptive Web Design. Possibly, in the future, also code examples.
Answers to common objections against using HTML as the media type for your API is found here: http://codeartisan.blogspot.se/2012/07/using-html-as-media-type-for-your-api.html


Use two different URLs for web and API
-------
Since you might want to split the solution in the future, more whatever reason, it's good to create such an option right from the start. The simplest way seems to be to have a duplicated DNS entry, pointing to the same IP.


Different flow for humans and machines
-------

My opinion now is it's to much work to separate responses between humans and machines. The "problem" was that the PRG pattern is needed for humans but not for machines. This twitter conversation made me change my mind: https://twitter.com/stilkov/status/335784329449984000
So, use the PRG pattern for both humans and machines - a redirect is interpreted as success and the clint can choose to follow the URL in the redirect or not.


Client support for HTML
-----------------------
There are several HTML parser for all possible application platforms out there. I think that parsers with CSS3 syntax (or, think jQuery selector).
Here are some I've found:
 - .NET: https://github.com/jamietre/CsQuery
 - Java: http://jsoup.org/cookbook/extracting-data/selector-syntax
 - iOS: Not any known libraries.. (?)
 - Ruby: https://www.engineyard.com/blog/2010/getting-started-with-nokogiri/
 - node: https://github.com/MatthewMueller/cheerio
 - lua: https://github.com/wscherphof/lua-htmlparser

Resouces
--------
Blog post: http://www.jayway.com/2012/08/01/combining-html-hypermedia-apis-and-adaptive-web-design/ (lots of links here)
Video of presentation: http://www.youtube.com/watch?v=YCjaOrIhYGg
Slides: http://www.slideshare.net/GustafKotte/html-hypermedia-apis-and-adaptive-web-design-nordic-apis

