<p><strong>WHOIS</strong></p>
<table>
  <tr>
    <th>Command</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>export TARGET="domain.tld"</td>
    <td>Assign target to an environment variable.</td>
  </tr>
  <tr>
    <td>whois $TARGET</td>
    <td>WHOIS lookup for the target.</td>
  </tr>
</table>

<p><strong>DNS Enumeration</strong></p>
<table>
  <tr>
    <th>Command</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>nslookup $TARGET</td>
    <td>Identify the A record for the target domain.</td>
  </tr>
  <tr>
    <td>nslookup -query=A $TARGET</td>
    <td>Identify the A record for the target domain.</td>
  </tr>
  <tr>
    <td>dig $TARGET @&lt;nameserver/IP&gt;</td>
    <td>Identify the A record for the target domain.</td>
  </tr>
  <tr>
    <td>dig a $TARGET @&lt;nameserver/IP&gt;</td>
    <td>Identify the A record for the target domain.</td>
  </tr>
  <tr>
    <td>nslookup -query=PTR &lt;IP&gt;</td>
    <td>Identify the PTR record for the target IP address.</td>
  </tr>
  <tr>
    <td>dig -x &lt;IP&gt; @&lt;nameserver/IP&gt;</td>
    <td>Identify the PTR record for the target IP address.</td>
  </tr>
  <tr>
    <td>nslookup -query=ANY $TARGET</td>
    <td>Identify ANY records for the target domain.</td>
  </tr>
  <tr>
    <td>dig any $TARGET @&lt;nameserver/IP&gt;</td>
    <td>Identify ANY records for the target domain.</td>
  </tr>
  <tr>
    <td>nslookup -query=TXT $TARGET</td>
    <td>Identify the TXT records for the target domain.</td>
  </tr>
  <tr>
    <td>dig txt $TARGET @&lt;nameserver/IP&gt;</td>
    <td>Identify the TXT records for the target domain.</td>
  </tr>
  <tr>
    <td>nslookup -query=MX $TARGET</td>
    <td>Identify the MX records for the target domain.</td>
  </tr>
  <tr>
    <td>dig mx $TARGET @&lt;nameserver/IP&gt;</td>
    <td>Identify the MX records for the target domain.</td>
  </tr>
</table>

<p><strong>Passive Subdomain Enumeration</strong></p>
<table>
  <tr>
    <th>Resource/Command</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>VirusTotal</td>
    <td><a href="https://www.virustotal.com/gui/home/url">https://www.virustotal.com/gui/home/url</a></td>
  </tr>
  <tr>
    <td>Censys</td>
    <td><a href="https://censys.io/">https://censys.io/</a></td>
  </tr>
  <tr>
    <td>Crt.sh</td>
    <td><a href="https://crt.sh/">https://crt.sh/</a></td>
  </tr>
  <tr>
    <td>curl -s https://sonar.omnisint.io/subdomains/{domain} | jq -r '.[]' | sort -u</td>
    <td>All subdomains for a given domain.</td>
  </tr>
  <tr>
    <td>curl -s https://sonar.omnisint.io/tlds/{domain} | jq -r '.[]' | sort -u</td>
    <td>All TLDs found for a given domain.</td>
  </tr>
  <tr>
    <td>curl -s https://sonar.omnisint.io/all/{domain} | jq -r '.[]' | sort -u</td>
    <td>All results across all TLDs for a given domain.</td>
  </tr>
  <tr>
    <td>curl -s https://sonar.omnisint.io/reverse/{ip} | jq -r '.[]' | sort -u</td>
    <td>Reverse DNS lookup on IP address.</td>
  </tr>
  <tr>
    <td>curl -s https://sonar.omnisint.io/reverse/{ip}/{mask} | jq -r '.[]' | sort -u</td>
    <td>Reverse DNS lookup of a CIDR range.</td>
  </tr>
  <tr>
    <td>curl -s "https://crt.sh/?q=${TARGET}&output=json" | jq -r '.[] | "\(.name_value)\n\(.common_name)"' | sort -u</td>
    <td>Certificate Transparency.</td>
  </tr>
  <tr>
    <td>cat sources.txt | while read source; do theHarvester -d "${TARGET}" -b $source -f "${source}-${TARGET}";done</td>
    <td>Searching for subdomains and other information on the sources provided in the source.txt list.</td>
  </tr>
</table>

<p><strong>Passive Infrastructure Identification</strong></p>
<table>
  <tr>
    <th>Resource/Command</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>Netcraft</td>
    <td><a href="https://www.netcraft.com/">https://www.netcraft.com/</a></td>
  </tr>
  <tr>
    <td>WayBackMachine</td>
    <td><a href="http://web.archive.org/">http://web.archive.org/</a></td>
  </tr>
  <tr>
    <td>WayBackURLs</td>
    <td><a href="https://github.com/tomnomnom/waybackurls">https://github.com/tomnomnom/waybackurls</a></td>
  </tr>
  <tr>
    <td>waybackurls -dates https://$TARGET &gt; waybackurls.txt</td>
    <td>Crawling URLs from a domain with the date it was obtained.</td>
  </tr>
</table>
