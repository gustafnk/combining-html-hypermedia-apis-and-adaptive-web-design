Combining HTML Hypermedia APIs and Adaptive Web Design
======================================================

Thoughts, issues and ideas on combining HTML Hypermedia APIs and Adaptive Web Design. Possibly, in the future, also code examples.

NB.  I will happily add collaborators and/or pull requests.

NB2.  Let's start with having everything in the README and when structure is found we refactor.

Answers to common objections against using HTML as the media type for your API is found here: http://codeartisan.blogspot.se/2012/07/using-html-as-media-type-for-your-api.html

Using the option for the future
-------
Assumption: humans browse on www.yourdomain.com, machines browse on api.yourdomain.com. Then, if we find ourselves in a unresolvable problem, we can split the solution, but perhaps just for that particular use-case - keeping the solution as tight as possible.
Here, another option is to take advantage of the different contexts. For example, returning a 201 Created for a machine, but redirecting a human to some main-page.


Different flow for humans and machines
-------
There seems to be some differences in how the application flow (with regards to writing data) can be handled for users and API clients. One problem seems to be the refresh button: either we:

1.  return a confirmation message to the user (with proper status code). In that case, the user will be less surprised of the "Send again?" dialog.
2.  return the resource (entity, list, etc), but then if the page is refreshed, a dialog will be shown.

I think that a pure (2) should be avoided. Instead, we can use server side code that does redirects )or not) depending on if the code is run in a browser context. How to detect "browser context" is up to the implementation, but I see these options at the moment:

1. Duplicated DNS entries pointing to the same IP (www., api.). Server code detects host name and act accordingly.
2. Separate running instances of the same code. Server code detects host name and/or port.
3. Build configuration, writing to a constant in the code. Deployed as separate instances. Detect constant.
4. Content negotiation. Would be hard to browse the API for a developer.
 
An example of (2) can be found here: https://github.com/gustafnk/RestBugs


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

