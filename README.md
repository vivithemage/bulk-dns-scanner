# Bulk DNS Scanner
Scans a domain and attemps to identify records using a predefined list of subdomains and record types.

Run using:

	python scan.py

To use, please copy the following into your project.

	scanner = BulkDNSScan()
    	results = scanner.run('example.com')
    	print(results)

It returns a dict which looks something along the lines of:

	{'__root': {'NS': [<DNS IN NS rdata: a.iana-servers.net.>, <DNS IN NS rdata: b.iana-servers.net.>], 'MX': None, 'A': [<DNS IN A rdata: 93.184.216.34>], 'TXT': [<DNS IN TXT rdata: "$Id: example.com 4415 2015-08-24 20:12:23Z davids $">, <DNS IN TXT rdata: "v=spf1 -all">], 'CNAME': None, 'AAAA': [<DNS IN AAAA rdata: 2606:2800:220:1:248:1893:25c8:1946>]}, 'www': {'NS': None, 'MX': None, 'A': [<DNS IN A rdata: 93.184.216.34>], 'TXT': [<DNS IN TXT rdata: "v=spf1 -all">], 'CNAME': None, 'AAAA': [<DNS IN AAAA rdata: 2606:2800:220:1:248:1893:25c8:1946>]}, 'mail': {'NS': None, 'MX': None, 'A': None, 'TXT': None, 'CNAME': None, 'AAAA': None}}

Your own subdomain and record lists can be passed:

	subdomain_list = ['dev', 'test', 'vps'];
	record_type_list = ['NS', 'MX', 'A', 'AAAA']
	
	scanner = BulkDNSScan()
	scanner.run()
