---
description: curl linux command cheatsheet by Thamizhiniyan C S
---

# curl

## Introduction

curl is a tool for transferring data from or to a server using URLs. It supports these protocols: DICT, FILE, FTP, FTPS, GOPHER, GOPHERS, HTTP, HTTPS, IMAP, IMAPS, LDAP, LDAPS, MQTT, POP3, POP3S, RTMP, RTMPS, RTSP, SCP, SFTP, SMB, SMBS, SMTP, SMTPS, TELNET, TFTP, WS and WSS.

***

## Syntax

`curl [options...]`

***

## Important Flags

<table><thead><tr><th width="201">Flags</th><th>Description</th></tr></thead><tbody><tr><td><code>-#</code></td><td>Will display a progress meter for you to know how much the download has progressed.(or use --silent flag for a silent crawl)</td></tr><tr><td><code>-o</code></td><td>Saves the file downloaded with the name given following the flag.</td></tr><tr><td><code>-O</code></td><td>Saves the file with the name it was saved on the server.</td></tr><tr><td><code>-C -</code></td><td>This flag can resume your broken download without specifying an offset.</td></tr><tr><td><code>--limit-rate</code></td><td>Limits the download/upload rate to somewhere near the specified range (Units in 100K,100M,100G)</td></tr><tr><td><code>-u</code></td><td>Provides user authentication (Format: -u user:password)</td></tr><tr><td><code>-T</code></td><td>Helps in uploading the file to some server(In our case php-reverse-shell)</td></tr><tr><td><code>-x</code></td><td>If you have to view the page through a PROXY. You can specify the proxy server with this flag. (-x proxy.server.com -u user:password(Authentication for proxy server))</td></tr><tr><td><code>-I</code></td><td>(Caps i) Queries the header and not the webpage.</td></tr><tr><td><code>-A</code></td><td>You can specify user agent to make request to the server</td></tr><tr><td><code>-L</code></td><td>Tells curl to follow redirects</td></tr><tr><td><code>-b</code></td><td>This flag allows you to specify cookies while making a curl request(Cookie should be in the format "NAME1=VALUE1;NAME2=VALUE2")</td></tr><tr><td><code>-d</code></td><td>This flag can be used to POST data to the server(generally used for posting form data).</td></tr><tr><td><code>-X</code></td><td>To specify the HTTP method on the URL. (GET,POST,TRACE,OPTIONS)</td></tr></tbody></table>

***

## Examples

<table><thead><tr><th width="435">Command</th><th>Description</th></tr></thead><tbody><tr><td><pre class="language-bash"><code class="lang-bash">curl -h
</code></pre></td><td>cURL help menu</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">curl inlanefreight.com
</code></pre></td><td>Basic GET request</td></tr><tr><td><p></p><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">curl -s -O inlanefreight.com/index.html
</code></pre></td><td>Download file</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">curl -k https://inlanefreight.com
</code></pre></td><td>Skip HTTPS (SSL) certificate validation</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">curl inlanefreight.com -v
</code></pre></td><td>Print full HTTP request/response details</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">curl -I https://www.inlanefreight.com
</code></pre></td><td>Send HEAD request (only prints response headers)</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">curl -i https://www.inlanefreight.com
</code></pre></td><td>Print response headers and response body</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">curl https://www.inlanefreight.com -A 'Mozilla/5.0'
</code></pre></td><td>Set User-Agent header</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">curl -u admin:admin http://&#x3C;SERVER_IP>:&#x3C;PORT>/
</code></pre></td><td>Set HTTP basic authorization credentials</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">curl http://admin:admin@&#x3C;SERVER_IP>:&#x3C;PORT>/
</code></pre></td><td>Pass HTTP basic authorization credentials in the URL</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">curl -H 'Authorization: Basic YWRtaW46YWRtaW4=' http://&#x3C;SERVER_IP>:&#x3C;PORT>/
</code></pre></td><td>Set request header</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">curl 'http://&#x3C;SERVER_IP>:&#x3C;PORT>/search.php?search=le'
</code></pre></td><td>Pass GET parameters</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">curl -X POST -d 'username=admin&#x26;password=admin' http://&#x3C;SERVER_IP>:&#x3C;PORT>/
</code></pre></td><td>Send POST request with POST data</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">curl -b 'PHPSESSID=c1nsa6op7vtk7kdis7bcnbadf1' http://&#x3C;SERVER_IP>:&#x3C;PORT>/
</code></pre></td><td>Set request cookies</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">curl -X POST -d '{"search":"london"}' -H 'Content-Type: application/json' http://&#x3C;SERVER_IP>:&#x3C;PORT>/search.php
</code></pre></td><td>Send POST request with JSON data</td></tr></tbody></table>

### **APIs**

<table><thead><tr><th width="433">Command</th><th>Description</th></tr></thead><tbody><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">curl http://&#x3C;SERVER_IP>:&#x3C;PORT>/api.php/city/london
</code></pre></td><td>Read entry</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">curl -s http://&#x3C;SERVER_IP>:&#x3C;PORT>/api.php/city/ | jq
</code></pre></td><td>jq</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">curl -X POST http://&#x3C;SERVER_IP>:&#x3C;PORT>/api.php/city/ -d '{"city_name":"HTB_City", "country_name":"HTB"}' -H 'Content-Type: application/json'
</code></pre></td><td>Create (add) entry</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">curl -X PUT http://&#x3C;SERVER_IP>:&#x3C;PORT>/api.php/city/london -d '{"city_name":"New_HTB_City", "country_name":"HTB"}' -H 'Content-Type: application/json'
</code></pre></td><td>Update (modify) entry</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">curl -X DELETE http://&#x3C;SERVER_IP>:&#x3C;PORT>/api.php/city/New_HTB_City
</code></pre></td><td>Delete entry</td></tr></tbody></table>
