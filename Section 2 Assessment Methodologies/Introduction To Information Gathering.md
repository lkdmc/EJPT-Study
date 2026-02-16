- First step of pen test
- The more info, the more successful
- Passive Information Gathering
	- IP, DNS, domain names, domain ownership, email, social media, web, subdomains
- Active Information Gathering
	- Open ports, internal infrastructure of a target network.
	- Enumerating information from target systems.


## Target Scoping

- process of defining what systems, networks, or applications
- Only what has been explicitly authorized.
- What am I allowed to collect information about?

	### Common Types of Targets
	- Domain-Based Targets
		- ex) example.com
		- testsite.local
	- A domain-based scope may include:
		- The primary domain
	- IP-Based Targets
		- 192.168.1.10
#### Scope
- In-Scope
	- Assets you are allowed to:
		- Collect information from
		- Scan
		- Enumerate
- Out of Scope
	- Assets you must not interact with
		- Third-party services
		- External domains not listed in scope
		- Systems owned by another organization

## Passive vs Active Reconnaissance (정찰)

- Passive
	- No direct connection
	- Low risk of detection
	- Usually performed first
	- ex)
		- Domain registration information
		- DNS records
		- Public website content
		- Search engine results
		- Publicly available email addresses

- Active
	- Sends traffic to the target (server, network) - NMAP, Brute-force
	- Increased visibility
	- Typically performed after passive recon
	- ex)
		- Live hosts
		- Open ports
		- Running services
		- Network responses

- ![[Pasted image 20260216223823.png]]

#### Recon Strategy
- Step 1: Define the target
	- Identify the domain, IP address, or network range
	- Confirm what is in scope
- Step 2: Perform Passive Reconnaissance
	- Gather public information
	- Identify potential attack surfaces
	- Build initial understanding of the target
- Step 3: Perform Active Reconnaissance
	- Discover live hosts
	- Identify open ports
	- Detect exposed services
- Step 4: Document & Organize your findings
	- Record domains, IPs, and ports
	- Prepare information for enumeration
	- Avoid repeating work later