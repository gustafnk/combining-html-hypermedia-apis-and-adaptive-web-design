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

I think that a pure (2) should be avoided. Instead, one of the following alternatives per use case could be chosen from:
1.  Use another form of redirect that most browsers would understand, i.e. <meta>-redirect or JavaScript redirect.
2.  Use a component that does redirects (given an argument for each use case) if in the browser context (see above, we can use www. and api. for different contexts) TODO: develop prototype for this 
3.  Split the use case into one part for browsers and one for API clients

All of these solutions would return proper status codes and still allow good flow for browser users.

Usage of non-semantic CSS grids, i.e. Twitter Bootstrap
-------------------------------------------------------
It's not good to clutter down your HTML with non-semantic classes. Instead, use a framework that allows for semantic grids. I think that http://compass-style.org has support for this.

Client support for HTML
-----------------------
There are several HTML parser for all possible application platforms out there. I think that parsers with CSS3 syntax (or, think jQuery selector).
Here are some I've found:
 - .NET: https://github.com/jamietre/CsQuery
 - Java: http://jsoup.org/cookbook/extracting-data/selector-syntax
 - iOS: Not any known libraries.. (?)
 - Ruby: https://www.engineyard.com/blog/2010/getting-started-with-nokogiri/
 - node: https://github.com/MatthewMueller/cheerio

Resouces
--------
http://www.jayway.com/2012/08/01/combining-html-hypermedia-apis-and-adaptive-web-design/ (lots of links here)
http://www.slideshare.net/GustafKotte/surviving-the-zombie-apocalpyse-of-connected-devices
