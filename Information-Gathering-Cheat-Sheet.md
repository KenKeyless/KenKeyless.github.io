
<h2>WHOIS</h2>
<div class="table-responsive"><table class="table table-striped text-left">
<thead>
<tr>
<th><strong>Command</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><code>export TARGET="domain.tld"</code></td>
<td>Assign target to an environment variable.</td>
</tr>
<tr>
<td><code>whois $TARGET</code></td>
<td>WHOIS lookup for the target.</td>
</tr>
</tbody>
</table></div>
<hr>
<h2>DNS Enumeration</h2>
<div class="table-responsive"><table class="table table-striped text-left">
<thead>
<tr>
<th><strong>Command</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><code>nslookup $TARGET</code></td>
<td>Identify the <code>A</code> record for the target domain.</td>
</tr>
<tr>
<td><code>nslookup -query=A $TARGET</code></td>
<td>Identify the <code>A</code> record for the target domain.</td>
</tr>
<tr>
<td><code>dig $TARGET @&lt;nameserver/IP&gt;</code></td>
<td>Identify the <code>A</code> record for the target domain.</td>
</tr>
<tr>
<td><code>dig a $TARGET @&lt;nameserver/IP&gt;</code></td>
<td>Identify the <code>A</code> record for the target domain.</td>
</tr>
<tr>
<td><code>nslookup -query=PTR &lt;IP&gt;</code></td>
<td>Identify the <code>PTR</code> record for the target IP address.</td>
</tr>
<tr>
<td><code>dig -x &lt;IP&gt; @&lt;nameserver/IP&gt;</code></td>
<td>Identify the <code>PTR</code> record for the target IP address.</td>
</tr>
<tr>
<td><code>nslookup -query=ANY $TARGET</code></td>
<td>Identify <code>ANY</code> records for the target domain.</td>
</tr>
<tr>
<td><code>dig any $TARGET @&lt;nameserver/IP&gt;</code></td>
<td>Identify <code>ANY</code> records for the target domain.</td>
</tr>
<tr>
<td><code>nslookup -query=TXT $TARGET</code></td>
<td>Identify the <code>TXT</code> records for the target domain.</td>
</tr>
<tr>
<td><code>dig txt $TARGET @&lt;nameserver/IP&gt;</code></td>
<td>Identify the <code>TXT</code> records for the target domain.</td>
</tr>
<tr>
<td><code>nslookup -query=MX $TARGET</code></td>
<td>Identify the <code>MX</code> records for the target domain.</td>
</tr>
<tr>
<td><code>dig mx $TARGET @&lt;nameserver/IP&gt;</code></td>
<td>Identify the <code>MX</code> records for the target domain.</td>
</tr>
</tbody>
</table></div>
<hr>
<h2>Passive Subdomain Enumeration</h2>
<div class="table-responsive"><table class="table table-striped text-left">
<thead>
<tr>
<th><strong>Resource/Command</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><code>VirusTotal</code></td>
<td><a href="https://www.virustotal.com/gui/home/url">https://www.virustotal.com/gui/home/url</a></td>
</tr>
<tr>
<td><code>Censys</code></td>
<td><a href="https://censys.io/">https://censys.io/</a></td>
</tr>
<tr>
<td><code>Crt.sh</code></td>
<td><a href="https://crt.sh/">https://crt.sh/</a></td>
</tr>
<tr>
<td><code>curl -s https://sonar.omnisint.io/subdomains/{domain} | jq -r '.[]' | sort -u</code></td>
<td>All subdomains for a given domain.</td>
</tr>
<tr>
<td><code>curl -s https://sonar.omnisint.io/tlds/{domain} | jq -r '.[]' | sort -u</code></td>
<td>All TLDs found for a given domain.</td>
</tr>
<tr>
<td><code>curl -s https://sonar.omnisint.io/all/{domain} | jq -r '.[]' | sort -u</code></td>
<td>All results across all TLDs for a given domain.</td>
</tr>
<tr>
<td><code>curl -s https://sonar.omnisint.io/reverse/{ip} | jq -r '.[]' | sort -u</code></td>
<td>Reverse DNS lookup on IP address.</td>
</tr>
<tr>
<td><code>curl -s https://sonar.omnisint.io/reverse/{ip}/{mask} | jq -r '.[]' | sort -u</code></td>
<td>Reverse DNS lookup of a CIDR range.</td>
</tr>
<tr>
<td><code>curl -s "https://crt.sh/?q=${TARGET}&amp;output=json" | jq -r '.[] | "\(.name_value)\n\(.common_name)"' | sort -u</code></td>
<td>Certificate Transparency.</td>
</tr>
<tr>
<td><code>cat sources.txt | while read source; do theHarvester -d "${TARGET}" -b $source -f "${source}-${TARGET}";done</code></td>
<td>Searching for subdomains and other information on the sources provided in the source.txt list.</td>
</tr>
</tbody>
</table></div>
<h4>Sources.txt</h4>
<div class="window_container"><div class="window_content"><div class="window_top">Code: <span class="text-success">txt</span></div><pre class=" language-txt"><code class=" language-txt">baidu
bufferoverun
crtsh
hackertarget
otx
projecdiscovery
rapiddns
sublist3r
threatcrowd
trello
urlscan
vhost
virustotal
zoomeye
</code></pre></div></div>
<hr>
<h2>Passive Infrastructure Identification</h2>
<div class="table-responsive"><table class="table table-striped text-left">
<thead>
<tr>
<th><strong>Resource/Command</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Netcraft</code></td>
<td><a href="https://www.netcraft.com/">https://www.netcraft.com/</a></td>
</tr>
<tr>
<td><code>WayBackMachine</code></td>
<td><a href="http://web.archive.org/">http://web.archive.org/</a></td>
</tr>
<tr>
<td><code>WayBackURLs</code></td>
<td><a href="https://github.com/tomnomnom/waybackurls">https://github.com/tomnomnom/waybackurls</a></td>
</tr>
<tr>
<td><code>waybackurls -dates https://$TARGET &gt; waybackurls.txt</code></td>
<td>Crawling URLs from a domain with the date it was obtained.</td>
</tr>
</tbody>
</table></div>
<hr>
<h2>Active Infrastructure Identification</h2>
<div class="table-responsive"><table class="table table-striped text-left">
<thead>
<tr>
<th><strong>Resource/Command</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><code>curl -I "http://${TARGET}"</code></td>
<td>Display HTTP headers of the target webserver.</td>
</tr>
<tr>
<td><code>whatweb -a https://www.facebook.com -v</code></td>
<td>Technology identification.</td>
</tr>
<tr>
<td><code>Wappalyzer</code></td>
<td><a href="https://www.wappalyzer.com/">https://www.wappalyzer.com/</a></td>
</tr>
<tr>
<td><code>wafw00f -v https://$TARGET</code></td>
<td>WAF Fingerprinting.</td>
</tr>
<tr>
<td><code>Aquatone</code></td>
<td><a href="https://github.com/michenriksen/aquatone">https://github.com/michenriksen/aquatone</a></td>
</tr>
<tr>
<td><code>cat subdomain.list | aquatone -out ./aquatone -screenshot-timeout 1000</code></td>
<td>Makes screenshots of all subdomains in the subdomain.list.</td>
</tr>
</tbody>
</table></div>
<hr>
<h2>Active Subdomain Enumeration</h2>
<div class="table-responsive"><table class="table table-striped text-left">
<thead>
<tr>
<th><strong>Resource/Command</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><code>HackerTarget</code></td>
<td><a href="https://hackertarget.com/zone-transfer/">https://hackertarget.com/zone-transfer/</a></td>
</tr>
<tr>
<td><code>SecLists</code></td>
<td><a href="https://github.com/danielmiessler/SecLists">https://github.com/danielmiessler/SecLists</a></td>
</tr>
<tr>
<td><code>nslookup -type=any -query=AXFR $TARGET nameserver.target.domain</code></td>
<td>Zone Transfer using Nslookup against the target domain and its nameserver.</td>
</tr>
<tr>
<td><code>gobuster dns -q -r "${NS}" -d "${TARGET}" -w "${WORDLIST}" -p ./patterns.txt -o "gobuster_${TARGET}.txt"</code></td>
<td>Bruteforcing subdomains.</td>
</tr>
</tbody>
</table></div>
<hr>
<h2>Virtual Hosts</h2>
<div class="table-responsive"><table class="table table-striped text-left">
<thead>
<tr>
<th><strong>Resource/Command</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><code>curl -s http://192.168.10.10 -H "Host: randomtarget.com"</code></td>
<td>Changing the HOST HTTP header to request a specific domain.</td>
</tr>
<tr>
<td><code>cat ./vhosts.list | while read vhost;do echo "\n********\nFUZZING: ${vhost}\n********";curl -s -I http://&lt;IP address&gt; -H "HOST: ${vhost}.target.domain" | grep "Content-Length: ";done</code></td>
<td>Bruteforcing for possible virtual hosts on the target domain.</td>
</tr>
<tr>
<td><code>ffuf -w ./vhosts -u http://&lt;IP address&gt; -H "HOST: FUZZ.target.domain" -fs 612</code></td>
<td>Bruteforcing for possible virtual hosts on the target domain using <code>ffuf</code>.</td>
</tr>
</tbody>
</table></div>
<hr>
<h2>Crawling</h2>
<div class="table-responsive"><table class="table table-striped text-left">
<thead>
<tr>
<th><strong>Resource/Command</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><code>ZAP</code></td>
<td><a href="https://www.zaproxy.org/">https://www.zaproxy.org/</a></td>
</tr>
<tr>
<td><code>ffuf -recursion -recursion-depth 1 -u http://192.168.10.10/FUZZ -w /opt/useful/SecLists/Discovery/Web-Content/raft-small-directories-lowercase.txt</code></td>
<td>Discovering files and folders that cannot be spotted by browsing the website.</td>
</tr>
<tr>
<td><code>ffuf -w ./folders.txt:FOLDERS,./wordlist.txt:WORDLIST,./extensions.txt:EXTENSIONS -u http://www.target.domain/FOLDERS/WORDLISTEXTENSIONS</code></td>
<td>Mutated bruteforcing against the target web server.</td>
</tr>
</tbody>
</table>
</div>