Combining HTML Hypermedia APIs and Adaptive Web Design
======================================================

Thoughts, issues and ideas on combining HTML Hypermedia APIs and Adaptive Web Design. Possibly, in the future, also code examples.

NB. I will happily add collaborators and/or pull requests.
NB2. Let's start with having everything in the README and when structure is found we refactor.


Flow
-------
There seems to be some differences in how the application flow (with regards to writing data) can be handled for users and API clients.

@Jamie: could you clarify the problems here, I can't quite remember... :)

### Return "main page" on successful POSTs for a human, return 201 Created for a machine. (Or 202 for async creation)
First, if something goes wrong in the POST, a 4xx or 5xx would be a good response, together with a message body that explains the error to the user.
For the happy flow, 307 Temporary Redirect can be used, redirecting both the human and the machine some entry-point for the application or sub-area.


Using the option for the future
-------
Assumption: humans browse on www.yourdomain.com, machines browse on api.yourdomain.com. Then, if we find ourselves in a unresolvable problem, we can split the solution, but perhaps just for that particular use-case - keeping the solution as tight as possible.
Here, another option is to take advantage of the different contexts. For example, returning a 201 Created for a machine, but redirecting a human to some main-page.


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
