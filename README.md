# What is it?

Toolkit that works with Apex to control page generation using the
Page and Block method.

Pipeline allows content to be tagged as Served on Render, Served via ESI,
Served via Ajax which should allow us to create Pyramid applications that
render and serve a page in .5 seconds, allowing the remaining content to 
be added afterwards.

For example, a blog article request comes in.

The page request is handled, the content in the middle is set to serve
on render, the Sidebar menu is set to be served via an ESI include and
assembled by Varnish (or Akamai or an equivalent ESI proxycache), and
the social media buttons served via Ajax through late binding, and then 
finally the advertising blocks are rendered.

Our important content is served immediately while the rest of the page
is constructed.

Most of the early workings of Pesi will be incorporated in Apex-Pipeline
and deprecates Pesi.

Note: Can we get the TCP MTU and Window Size from the connection? If so,
we could specifically craft responses to fit within those boundaries, 
further speeding things up. Thank you to Per Buer for this inspiration.
