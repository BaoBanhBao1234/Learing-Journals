1. What is a Domain Name?
- ==A domain name is a human-readable name used to locate an Internet service, such as a website.==
- ==Computers communicate using IP addresses. DNS (Domain Name System) lets people use domain names instead of memorizing numerical IP addresses.==
- ==A domain name is not the same as a website or a web server. It is a name that DNS can resolve to information used to reach a service.==

2. Domain Name vs. URL
- ==A URL is the full address of a resource. It can include a scheme, domain name, port, path, query string, and fragment.==
- Example: in `https://developer.mozilla.org/en-US/docs/`, `==https` is the scheme==, ==`developer.mozilla.org` is the domain name==, and ==`/en-US/docs/` is the path.==
- ==A domain name is one part of a URL. The domain name alone does not identify a particular page or specify the connection scheme.==
- `www` is commonly used as a subdomain, but it is optional and is not required for a website to work.

3. Structure of a Domain Name
- ==Domain names consist of one or more labels separated by dots and are read from right to left, from the broader DNS level to more specific labels.==
- Example: `developer.mozilla.org`
+ ==`.org` is the top-level domain (TLD).==
+ ==`mozilla` is the second-level label under `.org`.==
+ ==`developer` is a subdomain of `mozilla.org`.==
- ==A domain name does not need to contain exactly three labels==. For example, `mozilla.org` and `developer.mozilla.org` are both domain names.
- ==Common TLD categories include generic TLDs== such as `.com`, `.org`, and `.net`, ==and country-code TLDs== such as `.uk` and `.jp`.
- ==Some TLDs or domain labels have registration rules; the rules depend on the particular TLD and its registry.==

4. How DNS Uses a Domain Name
- ==When a user enters a domain name, the device first checks whether it already has a usable DNS answer in its cache.==
- ==If it does not, a DNS resolver looks up the name through the DNS hierarchy and obtains records from the authoritative DNS servers for that domain.==
- ==DNS records can provide IP addresses and other service information. The resolver caches answers for a limited time, so updates may not appear everywhere immediately.==
- ==After the device has the information needed to reach the service, it can connect to the server and request the resource.==
- ==DNS maps names to network information; it does not store or deliver the website's page content.==

5. Domain Registration
- ==A domain name must be available and registered before one person or organization can use it under the applicable rules.==
- ==A registrar is a company or organization that lets customers register and manage domain names. A registry maintains the registration database for a TLD.==
- ==Registering a domain does not mean buying it permanently. The registrant receives the right to use it for a defined period and must renew it to keep using it.==
- When choosing a registrar, review the registration price, renewal price, renewal and expiration policies, and account security options.
- After a domain is registered or its DNS settings change, cached DNS answers may remain in use until their time-to-live (TTL) expires.

6. Choosing and Managing a Domain Name
- Choose a name that is easy to recognize, spell, and remember.
- Select a TLD that suits the purpose of the site and check whether that TLD has special registration requirements.
- Check spelling carefully before completing registration.
- Keep control of the registrar account and its recovery details, enable available account security features, and renew the registration before it expires.
- A domain name can point to a website, email service, or other Internet service through its DNS records. Registration alone does not provide web hosting.

7. Key Takeaways
- A domain name is a readable name that helps people reach an Internet service; DNS resolves it to network information.
- A URL is a complete resource address, while the domain name is only one part of that address.
- TLDs and other labels form a hierarchy, and subdomains can be created under a registered domain.
- Domain registration grants time-limited use and must be renewed.
- Domain registration, DNS configuration, and web hosting are related but separate things.

8. Sources
- What is a Domain Name? https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_domain_name
- Cloudflare: What is a domain name? Domain names vs. URLs https://www.cloudflare.com/en-gb/learning/dns/glossary/what-is-a-domain-name/
- Create a Pro Website: A Beginner's Guide to How Domain Names Work! (YouTube) https://www.youtube.com/watch?v=Y4cRx19nhJk
- Everything You Need to Know about Domain Names (YouTube) https://www.youtube.com/watch?v=qO5qcQgiNX4
