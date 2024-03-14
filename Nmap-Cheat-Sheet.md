<h2>Scanning Options</h2>
<div class="table-responsive"><table class="table table-striped text-left">
<thead>
<tr>
<th><strong>Nmap Option</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><code>10.10.10.0/24</code></td>
<td>Target network range.</td>
</tr>
<tr>
<td><code>-sn</code></td>
<td>Disables port scanning.</td>
</tr>
<tr>
<td><code>-Pn</code></td>
<td>Disables ICMP Echo Requests</td>
</tr>
<tr>
<td><code>-n</code></td>
<td>Disables DNS Resolution.</td>
</tr>
<tr>
<td><code>-PE</code></td>
<td>Performs the ping scan by using ICMP Echo Requests against the target.</td>
</tr>
<tr>
<td><code>--packet-trace</code></td>
<td>Shows all packets sent and received.</td>
</tr>
<tr>
<td><code>--reason</code></td>
<td>Displays the reason for a specific result.</td>
</tr>
<tr>
<td><code>--disable-arp-ping</code></td>
<td>Disables ARP Ping Requests.</td>
</tr>
<tr>
<td><code>--top-ports=&lt;num&gt;</code></td>
<td>Scans the specified top ports that have been defined as most frequent.</td>
</tr>
<tr>
<td><code>-p-</code></td>
<td>Scan all ports.</td>
</tr>
<tr>
<td><code>-p22-110</code></td>
<td>Scan all ports between 22 and 110.</td>
</tr>
<tr>
<td><code>-p22,25</code></td>
<td>Scans only the specified ports 22 and 25.</td>
</tr>
<tr>
<td><code>-F</code></td>
<td>Scans top 100 ports.</td>
</tr>
<tr>
<td><code>-sS</code></td>
<td>Performs an TCP SYN-Scan.</td>
</tr>
<tr>
<td><code>-sA</code></td>
<td>Performs an TCP ACK-Scan.</td>
</tr>
<tr>
<td><code>-sU</code></td>
<td>Performs an UDP Scan.</td>
</tr>
<tr>
<td><code>-sV</code></td>
<td>Scans the discovered services for their versions.</td>
</tr>
<tr>
<td><code>-sC</code></td>
<td>Perform a Script Scan with scripts that are categorized as "default".</td>
</tr>
<tr>
<td><code>--script &lt;script&gt;</code></td>
<td>Performs a Script Scan by using the specified scripts.</td>
</tr>
<tr>
<td><code>-O</code></td>
<td>Performs an OS Detection Scan to determine the OS of the target.</td>
</tr>
<tr>
<td><code>-A</code></td>
<td>Performs OS Detection, Service Detection, and traceroute scans.</td>
</tr>
<tr>
<td><code>-D RND:5</code></td>
<td>Sets the number of random Decoys that will be used to scan the target.</td>
</tr>
<tr>
<td><code>-e</code></td>
<td>Specifies the network interface that is used for the scan.</td>
</tr>
<tr>
<td><code>-S 10.10.10.200</code></td>
<td>Specifies the source IP address for the scan.</td>
</tr>
<tr>
<td><code>-g</code></td>
<td>Specifies the source port for the scan.</td>
</tr>
<tr>
<td><code>--dns-server &lt;ns&gt;</code></td>
<td>DNS resolution is performed by using a specified name server.</td>
</tr>
</tbody>
</table></div>
<h2>Output Options</h2>
<div class="table-responsive"><table class="table table-striped text-left">
<thead>
<tr>
<th><strong>Nmap Option</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><code>-oA filename</code></td>
<td>Stores the results in all available formats starting with the name of "filename".</td>
</tr>
<tr>
<td><code>-oN filename</code></td>
<td>Stores the results in normal format with the name "filename".</td>
</tr>
<tr>
<td><code>-oG filename</code></td>
<td>Stores the results in "grepable" format with the name of "filename".</td>
</tr>
<tr>
<td><code>-oX filename</code></td>
<td>Stores the results in XML format with the name of "filename".</td>
</tr>
</tbody>
</table></div>
<h2>Performance Options</h2>
<div class="table-responsive"><table class="table table-striped text-left">
<thead>
<tr>
<th><strong>Nmap Option</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><code>--max-retries &lt;num&gt;</code></td>
<td>Sets the number of retries for scans of specific ports.</td>
</tr>
<tr>
<td><code>--stats-every=5s</code></td>
<td>Displays scan's status every 5 seconds.</td>
</tr>
<tr>
<td><code>-v/-vv</code></td>
<td>Displays verbose output during the scan.</td>
</tr>
<tr>
<td><code>--initial-rtt-timeout 50ms</code></td>
<td>Sets the specified time value as initial RTT timeout.</td>
</tr>
<tr>
<td><code>--max-rtt-timeout 100ms</code></td>
<td>Sets the specified time value as maximum RTT timeout.</td>
</tr>
<tr>
<td><code>--min-rate 300</code></td>
<td>Sets the number of packets that will be sent simultaneously.</td>
</tr>
<tr>
<td><code>-T &lt;0-5&gt;</code></td>
<td>Specifies the specific timing template.</td>
</tr>
</tbody>
</table></div>
</div>