1. What is a Web Browser?
- A web browser is an application that retrieves web resources from servers and presents them as pages or interactive applications.
- Users can navigate by entering a URL, selecting a link, or submitting a form.
- A browser is different from a search engine: a browser is software for accessing the Web, while a search engine is a website or service that helps users find web content.
- Examples of browsers include Chrome, Firefox, Safari, and Edge. Browsers may use different rendering engines and can display the same site somewhat differently.

2. Main Browser Components
- User interface:
+ Includes browser controls such as the address bar, tabs, navigation buttons, bookmarks, and menus.
- Browser engine:
+ Coordinates work between the user interface and the browser's other components.
- Rendering engine:
+ Parses web documents and turns HTML and CSS into a visual page.
+ Examples include Blink, WebKit, and Gecko; exact browser architecture varies.
- Networking component:
+ Fetches documents and other resources over network protocols such as HTTP and HTTPS.
- JavaScript engine:
+ Parses and executes JavaScript so pages can respond to user input and update dynamically.
- Data storage:
+ Stores information such as cache data, cookies, local storage, and browsing history, depending on user settings and site permissions.
- Modern browsers also include security features, such as isolating site processes and controlling access to sensitive device capabilities.

3. What Happens When You Open a Web Page?
- A user enters a URL or follows a link. The browser parses the URL to determine the scheme, hostname, path, and other request information.
- The browser finds the server's network address. It may use a cached DNS result; otherwise, it performs a DNS lookup for the hostname.
- The browser establishes a connection to the server. For HTTPS, it negotiates a TLS-protected connection so the server can be authenticated and traffic can be encrypted in transit.
- The browser sends an HTTP request, commonly requesting the page's HTML document.
- The server returns an HTTP response containing the document and response metadata.
- As it processes the HTML, the browser discovers references to other resources, such as stylesheets, scripts, images, and fonts, and requests them as needed.
- The browser parses and renders the document. It can show content while additional resources are still loading.
- JavaScript may continue to update the page and handle user interactions after the first content appears.

4. How Browsers Parse and Render a Page
- The browser parses HTML and builds the **DOM (Document Object Model)**, a tree representation of the document's elements and content.
- It parses CSS and builds the **CSSOM (CSS Object Model)**, a representation of the styles that apply to the page.
- The browser combines the DOM and CSSOM to determine which visible elements to display and their computed styles.
- During **layout**, it calculates the size and position of elements based on the document and viewport.
- During **painting**, it draws text, colors, borders, images, and other visual parts as pixels.
- The browser may use **compositing** to combine separately drawn layers into the final image on screen.
- If content or styles change, the browser may need to recalculate styles, layout, or painting. Unnecessary repeated work can make pages feel slow or choppy.

5. JavaScript and Page Interactivity
- JavaScript can respond to actions such as clicks, typing, scrolling, and form submissions.
- Much browser work that affects rendering and interaction uses a main thread. Long-running JavaScript tasks can keep that thread busy and delay updates or input responses.
- Browsers can run some work in the background using mechanisms such as Web Workers, which do not directly manipulate the page's DOM.
- The `async` and `defer` attributes can affect when external scripts are fetched and executed. Their behavior should be chosen based on whether a script depends on document parsing or execution order.

6. Loading and Caching Resources
- A web page often consists of many resources hosted under one or more hostnames.
- The browser may cache DNS answers and downloaded resources, allowing later visits to reuse them when the cache rules permit.
- The browser can start fetching resources as it discovers them in the document; some browsers use a preload scanner to find important resources early.
- Network latency, bandwidth, server response time, resource size, and the number of required requests can all affect loading time.
- If an image's dimensions are unknown before it loads, the browser may need to recalculate the page layout after the image arrives. Supplying dimensions can help reserve space and reduce layout shifts.

7. Browser Security and Privacy
- HTTPS uses TLS to protect data exchanged between the browser and a website and to authenticate the server's identity.
- Browsers apply security boundaries and permissions to limit what websites can access. Site permissions can govern features such as location, camera, and microphone access.
- Modern browsers may isolate websites or browser tabs into separate processes or sandboxes to reduce the impact of malicious or compromised content. The details vary by browser.
- Private or incognito mode generally limits what the browser saves locally for that session, such as browsing history. It does not make a user anonymous to websites, network operators, or Internet providers.
- Keeping the browser updated helps users receive security fixes and compatibility improvements.

8. Browser Performance and User Experience
- Fast page loading depends on both network work and browser work, including parsing, style calculation, layout, painting, and script execution.
- A page may display its first content before it is fully loaded or fully interactive. These are different stages of the user experience.
- Large or blocking scripts can delay rendering or prevent the browser from responding smoothly to input.
- Efficient HTML, CSS, images, and JavaScript can reduce unnecessary work. Avoiding repeated layout changes and reserving space for media can also help keep a page visually stable.
- Browser implementations differ, so websites should be checked across relevant browsers and devices.

9. Key Takeaways
- A browser requests web resources, interprets web technologies, and presents the result for users to view and interact with.
- Loading a page involves navigation, DNS lookup when needed, a network connection, an HTTP request and response, and additional resource requests.
- The browser builds the DOM and CSSOM, calculates layout, paints pixels, and may composite layers to display a page.
- JavaScript makes pages interactive, but long tasks can delay rendering and user input.
- Browser caching, security boundaries, HTTPS, and user privacy settings all affect the browsing experience.

10. Sources
- Ramotion: What is a Web Browser? https://www.ramotion.com/blog/what-is-web-browser/
- MDN: Populating the page: how browsers work https://developer.mozilla.org/en-US/docs/Web/Performance/How_browsers_work
- YouTube video supplied with the request https://www.youtube.com/watch?v=5rLFYtXHo9s 
