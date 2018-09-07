Hello everyone! This project is forked from a repository set up to allow servers to crawl
URLs across UCI's ICS subdomains. 

The part that I implemented filters "bad" URLs. What are bad URLs?
Well, the idea of a crawler is to be able to:
  1. Load a queued webpage to be crawled
  2. Grab all the links on the page (anchor tags)
  3. Filter out bad and unwanted links
  4. Queue up the new links to be crawled
  5. Repeat

Crawler traps usually aren't intentional, but it slows the crawlers progress down to well... 
a crawl (a very slow one).

When a crawler gets "trapped", URLs will typically lead to other very similar URLs, and any new
links that it finds will continue to follow this pattern. Thus, the queue of the crawler's links
to crawl are taken over by essentially the same link.

In this program, the crawler will avoid dynamically generated links, and will limit links from the
same subdomain to a set maximum. This will prevent the crawler getting trapped on news links, which
are very prevalent across ICS subdomains.

After crawling a link, the crawler keeps track of each URL that it has crawled, and will create a
.txt file containing the names of subdomains crawled over, and how many URLs are in each subdomain.
