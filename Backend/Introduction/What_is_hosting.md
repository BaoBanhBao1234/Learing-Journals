1. What is Hosting?
- Web hosting is the service of storing a website's files on an Internet-connected computer (a web server) and making those files available to visitors' browsers.
- Hosting includes the website's HTML documents and related assets, such as images, CSS stylesheets, JavaScript files, fonts, and videos.
- A website can technically be hosted on a personal computer, but a dedicated web server is usually more convenient because it is typically available more consistently, remains connected to the Internet, can use a stable IP address, and is often maintained by a hosting provider.
- A hosting provider supplies or manages the server resources used to publish a website. Services vary in features and price, so the choice should fit the website's needs and budget.
- After obtaining a hosting service, the website files need to be uploaded to the web server.

2. Website, Web Server, and Hosting
- Web page: A document, usually written in HTML, that a browser can display. It may include styles, scripts, images, audio, and video.
- Website: A collection of related web pages and resources, usually connected by links and sharing a domain name.
- Web server: The computer that hosts one or more websites and sends their files to visitors' browsers.
- Hosting: The act or service of making a website's pages and associated files available on a web server.
- A web server can host multiple websites, so a website and its web server are different things.
- A web server also involves software. At a minimum, an HTTP server receives browser requests and returns the requested content.

3. How a Hosted Website Is Delivered
- A visitor enters a website address (URL) or follows a link in a browser.
- The browser sends an HTTP request for the requested resource to the appropriate web server.
- The HTTP server checks whether the URL matches a file it hosts.
- If the file exists, the server sends its contents back to the browser using HTTP.
- If the file is not available and the server cannot generate it, the server responds with an error, commonly `404 Not Found`.
- The browser uses the returned files to display the web page.

4. HTTP Basics
- HTTP (Hypertext Transfer Protocol) defines how a client, such as a browser, and a server exchange web resources.
- A protocol is a set of rules that devices follow when communicating.
- HTTP is textual: its commands and messages are represented as text.
- HTTP is stateless: each request is treated independently, and HTTP alone does not remember earlier interactions. Applications that need to remember information, such as a login or progress in a transaction, require additional application-side mechanisms.
- A server must respond to an HTTP request, either with the requested content or an error response.

5. Static and Dynamic Hosting
- Static hosting serves stored files as they are, without changing their content for each request. A static setup needs a computer and HTTP server software.
- Static websites are generally simpler to set up and are a good starting point for a first website.
- Dynamic hosting adds software, commonly an application server and a database, to a basic web server.
- The application server can process a request and generate or update a page before the HTTP server sends it to the browser.
- For example, an application server can fill an HTML template with content stored in a database. This lets a site with many pages use a smaller number of templates and a database, which can make its content easier to manage and deliver.
- Dynamic sites are more flexible, but their technology stack is more complex. The appropriate application server depends on the site's requirements; existing configurable software and server frameworks are commonly used instead of building everything from scratch.

6. Key Takeaways
- Hosting makes a website's files reachable over the Internet by storing them on a web server.
- The browser requests resources using URLs and HTTP; the server returns the requested files or an error.
- Static hosting returns files as stored, while dynamic hosting can generate or update content using application software and a database.
- Choosing a hosting service involves matching its availability, features, and cost to the website's needs.

7. Sources
- What is a web server? https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Web_mechanics/What_is_a_web_server
- Pages, sites, servers, and search engines (the supplied URL currently redirects to the broader "Browsing the web" article): https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Web_mechanics/Pages_sites_servers_and_search_engines
