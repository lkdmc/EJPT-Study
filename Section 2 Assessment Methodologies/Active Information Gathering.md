## DNS Zone transfers

### DNS Interrogation
- is the process of enumerating DNS records for a specific domain.
- is to probe a DNS server to provide us with DNS records for a specific domain.
- can provide with important information like the IP address of a domain, subdomains, mail server addresses etc.
- DNS정보를 얻는거 같다.
- 내부 infrastructure를 알 수 있다.
-

## Host Discovery With Nmap
- ex)
	- sudo netdiscover -i eth0 -r 
	- sudo nmap -sn {ip address}/{subnet mask}


## Port Scanning With Nmap
- nmap -Pn -p 80 {ip address} = search for port 80
- nmap -Pn -p1-1000 {ip address} = search for port 1 to 1000
- nmap -Pn -F {ip address} = search for available ports (entire)
	- nmap -Pn -F {ip address} -v = show the detail, -v means verbosity(다변, 장황한)
- nmap -Pn -sU {ip address} = search for UDP ports
- nmap -Pn -F -sV {ip address} = service version detection scan
- nmap -Pn -F -sV -O {ip address} = scan for operation system + service version
- nmap -Pn -F -sV -O -sC {ip address} =  show which nmap script used for scan
	- nmap -Pn -F -A {ip address} is the same 

#### NMAP Time template(higher is faster)
- -T0: paranoid
- -T1: sneaky
- -T2: polite
- -T3: normal
- -T4: aggressive
- -T5: insane
-ex) nmap -Pn -F -T5 -sV -O -sC {ip}

#### NMAP Documentation
- nmap -Pn -F {ip} -oN test.txt: normal format
	- -oX: XML format
	- -oG: grepable format
	- -oA: everything