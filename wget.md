---
description: wget linux command cheatsheet by Thamizhiniyan C S
---

# wget

## Introduction

GNU Wget is a free utility for non-interactive download of files from the Web. It supports HTTP, HTTPS, and FTP protocols, as well as retrieval through HTTP proxies.

***

## Syntax

`wget [option]... [URL]...`

***

## Important Flags

<table><thead><tr><th width="255">Flags</th><th>Description</th></tr></thead><tbody><tr><td><code>-b</code></td><td>To background the downloading process</td></tr><tr><td><code>-c</code></td><td>To continue to the partially downloaded file (It will look for the partially downloaded file in the directory and starts appending; takes no argument)</td></tr><tr><td><code>-t int</code></td><td>To specify retries to the URL</td></tr><tr><td><code>-O download.txt</code></td><td>To specify the output name of downloaded file</td></tr><tr><td><code>-o file</code></td><td>To overwrite the logs into another file</td></tr><tr><td><code>-a file</code></td><td>To append the logs into already existing file without deleting previous</td></tr><tr><td><code>-i file</code></td><td>Read the list of URLs from a file.</td></tr><tr><td><code>--user=username</code></td><td>To give a login username(Use --ftp-user and --http-user if doesn't work)</td></tr><tr><td><code>--password=password</code></td><td>To give a login password( Use --ftp-password and --http-password if doesn't work)</td></tr><tr><td><code>--ask-password</code></td><td>Ask for a password prompt if a login is necessary. (I recommend using this flag instead of --password because there are chances that password might start with $ or something else that can be interpreted as something else in your terminal)</td></tr><tr><td><code>--limit-rate=10k</code></td><td>Similarly to curl(supports k and m notation for kB and mB respectively)</td></tr><tr><td><code>-w=&#x3C;int></code></td><td>This is to specify the waiting time before the retrieval from a URL.(Takes time in seconds)</td></tr><tr><td><code>-T=&#x3C;int></code></td><td>Timeout the retrieval after a specified amount of time.(Takes time in seconds)</td></tr><tr><td><code>-N</code></td><td>Enables timestamping</td></tr><tr><td><code>-U</code></td><td>To specify the user-agent while downloading the file</td></tr></tbody></table>

***

## Examples

<table><thead><tr><th width="427">Command</th><th>Description</th></tr></thead><tbody><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">wget -O speedtest.zip ftp://speedtest.tele2.net/1MB.zip
</code></pre></td><td>Downloading a file with different file name</td></tr><tr><td><pre class="language-bash" data-overflow="wrap"><code class="lang-bash">wget -o log.txt -N ftp://speedtest.tele2.net/1MB.zip
</code></pre></td><td>Specifying logfile as log.txt with timestamping enabled</td></tr><tr><td><pre class="language-bash"><code class="lang-bash">wget -i file.txt --limit-rate=1mb    
</code></pre></td><td>Read URLs from "file.txt" and limit the download speed to 1mbps</td></tr></tbody></table>
