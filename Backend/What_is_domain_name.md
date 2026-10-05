1. What is Domain Name?
- Structure of Domain Name
+ A domain name has a simple structure made of several parts separated by dots and read from right to left
+ Each of these parts provides specific information about the whole domain name
- TLS (Top-Level Domain)
+ TLDs tell users the general purpose of the service behind the domain name. The most geneeic TLDs (.com, .org, .net, ...) don't require web services to meet any particular criteria, but some TLDs enforce stricter policies so it is clearer what them purpose is
Ex: Local TLDs: .us, .fr, .se can require the service to be provided in a given language or hosted in a certain country - tehy are supposted to indicate a resource in a particular language or country
    TLDs containing .gov are only allowed to be used by government departments
    The .edu TLD is only for use by educational and academic institutions
+ The full list of TLDs is maintained by ICANN 
- Label (or component)
+ The labels are what follow the TLD. A label is a case-insensitive character sequence anywhere from one to sixty-three characters is length, containing only the letters A through Z, digits 0 through 9 and the "-" character
+ The label located right before the TLD is also called a Secondary Level Domain (SLD)
+ A domain name can have many labels (or components). It is not mandatory nor necessary to have 3 labels to form a domain name
- Buying a domain name
+ Who own a domain name?
- - You cannot "buy a domain name". This is so that unused doamin names eventually become available to be used again by someone else. If every domain name was bought, the web would quickly fill up with unused domain names that were locked and couldn't be used by anyone
- - Instead, you can pay for the right to use domain name for one or more years. You can review your right and your renewal has priority over other people's applications. But you never own the domain name
- - Companies called registrars use domain name registries to keep track of technical and administrative information connecting you to your domain name
+ Find an available domain name
- - Go to a domain name registrar's website
- - Alternative, if you use a system with a built in shell. type a "whois" command into it 
+ Getting a domain name
- - Go to a domain name registrar's website\
- - Usually there is a prominent "GET" domain name call to action click on it
- - Fill out the form with all required details. Make sure, especially, that you have not misspelled your desired domain name
- - The registrar will let you know when the domain name is properly registered. Within a few hours, all DNS servers will have received your DNS information 
+ DNS refreshing
- - DNS databases are stored on every DNS server worldwide and all these servers refer to a few specail servers called "authoritative naem servers" or "top-level DNS servers" - there are like the boss servers that manage the system 
- - Whenever your registrar creates or updates any information for a given domain, the information must be refreshed in every DNS database. Each DNS server that knows about a given domain stores the information for some time before it is automatically invalidated and the refreshed (the DNS server queries an authoritative server and fetches the updated information from it). Thus, it takes some time for DNS servers that know about this doamin name to get the up-to-date information
2. What does a DNS request work?
- Type a domain name in your browser's location bar
- your browser asks your computer if it already recognizes the IP address identified by this domain name (using a local DNS cache). If it does, the name is translated to the IP address and the browser negotiates contents with the web server. End of story
- If  your computer does not know which IP is behind the domain name, it goes on to ask a DNS server, whose job is precisely to tell your computer which IP address matches each registered domain name
- Now that the computer knows the requested IP address, your browser can negotiate contents with the web server