1. What is DNS?
- DNS (Domain Name System) is a distributed, hierarchical naming system used to look up information about domain names.
- Its most familiar job is resolving a human-readable hostname, such as `www.example.com`, to an IP address that computers can use to reach a network service.
- DNS is often compared to an Internet phone book, but it stores different kinds of records, not only IP addresses.
- A DNS lookup happens behind the scenes when an application needs information about a hostname.

2. The Main DNS Components
- DNS client / stub resolver:
+ Runs on a user's device as part of the operating system's networking process.
+ Receives lookup requests from applications, checks local information, and asks a recursive resolver when needed.
- Recursive resolver:
+ Receives a query from the client and works to return the requested record or an error.
+ Often operated by an Internet service provider or a public DNS provider.
+ Checks its cache before querying other DNS servers.
- Root nameserver:
+ Knows where to find nameservers for top-level domains (TLDs), such as `.com` or `.org`.
+ Usually responds with a referral; it does not store the IP address for every website.
- TLD nameserver:
+ Handles a top-level domain such as `.com`.
+ Refers the resolver to the nameservers responsible for a particular domain, such as `example.com`.
- Authoritative nameserver:
+ Holds DNS records for a domain or DNS zone.
+ Returns the requested record from its zone data and is the final source for that record in the lookup chain.
- A recursive resolver and an authoritative nameserver have different jobs: the resolver finds an answer for the client, while the authoritative server provides the records for the domain it serves.

3. How a DNS Lookup Works
- Assume a user enters `www.example.com` and the answer is not already cached:
+ The browser or operating system checks available local DNS information, such as its cache or hosts file.
+ If it has no usable answer, the device's stub resolver sends a query to a recursive resolver. The query asks for a particular record type, for example an `A` record.
+ The recursive resolver checks its own cache. If it already has a valid answer, it returns it to the device and the remaining lookup steps are skipped.
+ If it needs to find the answer, the resolver asks a root nameserver where to find the `.com` TLD nameserver.
+ The resolver asks the `.com` TLD nameserver where to find the authoritative nameserver for `example.com`.
+ The resolver asks that authoritative nameserver for the requested record for `www.example.com`.
+ The authoritative server returns the record. The recursive resolver caches it for the record's permitted time and sends the answer to the device.
+ The browser can then connect to the returned IP address and send an HTTP request for the webpage.
- Root and TLD servers generally provide referrals to the next level; they do not provide the final website record.
- A cached answer may let the resolver skip some or all of these queries, so every page load does not necessarily contact the root servers.

4. Recursive and Iterative Queries
- A recursive query asks the resolver to return the requested answer, or an error if it cannot find one.
- An iterative query lets a DNS server return the best information it has, often a referral to another nameserver. The resolver follows that referral and continues the lookup.
- In a typical lookup, the client makes a recursive request to its resolver, and the resolver uses iterative queries to follow referrals through the DNS hierarchy.
- A non-recursive response can be returned when the queried server already has the answer in its cache or is authoritative for it.

5. Common DNS Record Types
- DNS records store different kinds of information. The requester specifies which type it wants.
+ `A`: maps a hostname to an IPv4 address.
+ `AAAA`: maps a hostname to an IPv6 address.
+ `CNAME`: makes one hostname an alias of another hostname.
+ `MX`: identifies mail servers that receive email for a domain.
+ `NS`: identifies nameservers responsible for a DNS zone or domain delegation.
+ `TXT`: stores text data, often used for domain verification and email-related configuration.
+ `PTR`: supports reverse DNS lookups, which look up a hostname from an IP address.

6. DNS Caching and TTL
- DNS answers may be cached by a browser, operating system, recursive resolver, or other DNS infrastructure.
- TTL (Time to Live) specifies how long a DNS record may be cached before it should be queried again.
- Caching reduces lookup time and the number of queries sent to other DNS servers.
- When a DNS record changes, users may continue to receive a previously cached answer until its TTL expires. This is why an update may not appear everywhere immediately; it does not mean DNS copies every record to every server.
- If a record is cached at a nearby resolver, the resolver may answer without contacting the root, TLD, or authoritative servers for each request.

7. DNSSEC
- DNSSEC (Domain Name System Security Extensions) adds digital signatures that allow validating resolvers to check the authenticity and integrity of DNS data.
- DNSSEC helps detect forged or altered DNS responses. It does not encrypt DNS queries or hide the domain being looked up.
- `dig example.com +dnssec` can request DNSSEC-related data when using `dig`; interpreting validation results depends on the resolver and the response.

8. Useful DNS Commands
- `dig` is a command-line utility for querying DNS. It is available by default on many Linux and macOS systems; on Windows, it may need to be installed. `nslookup` is another commonly available DNS lookup utility.
+ `dig example.com A`: look up the A record for a domain.
+ `dig +short example.com`: print a short answer.
+ `dig +trace example.com`: follow the delegation chain from the DNS root.
+ `dig example.com MX`: look up mail exchange records.
+ `dig example.com A @8.8.8.8`: query a particular recursive resolver.
- On Windows, `ipconfig /flushdns` clears the local DNS client cache.

9. Key Takeaways
- DNS looks up records associated with domain names; resolving names to IP addresses is its most familiar use.
- A recursive resolver finds answers for clients, while authoritative nameservers provide records for their zones.
- When needed, a resolver follows referrals from the DNS root to a TLD server and then to the domain's authoritative nameserver.
- Caching and TTLs make lookups faster, but can delay when a DNS change becomes visible to a particular user.
- After name resolution, the browser uses the returned information to connect to the web service.

10. Sources
- CS.FYI: Everything You Need to Know About DNS https://cs.fyi/guide/everything-you-need-to-know-about-dns
- Cloudflare: What Is DNS? https://www.cloudflare.com/en-gb/learning/dns/what-is-dns/
- How DNS Works: Interactive comic https://howdns.works/
- YouTube video supplied with the request https://www.youtube.com/watch?v=Wj0od2ag5sk 
