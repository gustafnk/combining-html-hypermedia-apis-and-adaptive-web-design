Combining HTML Hypermedia APIs and Adaptive Web Design
======================================================

Thoughts, Combining HTML Hypermedia APIs and Adaptive Web Design.

NB. Let's start with having everything in the README and when structure is found we refactor.


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


Resouces
--------
http://www.jayway.com/2012/08/01/combining-html-hypermedia-apis-and-adaptive-web-design/ (lots of links here)
http://www.slideshare.net/GustafKotte/surviving-the-zombie-apocalpyse-of-connected-devices
