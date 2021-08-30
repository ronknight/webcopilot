<h1 align="center"><a href="https://github.com/h4r5h1t-hrs/webcopilot/">WebCopilot</a></h1>
<h4 align="center">An automation tool that enumerate subdomains then filters out xss, sqli, open redirect, lfi, ssrf and rce parameters and then scans for vulnerabilities.</h4>

<p align="center">
<a href="https://twitter.com/h4r5h1t_hrs"><img src="https://img.shields.io/twitter/follow/h4r5h1t_hrs?style=social"></a>
<a href="https://github.com/h4r5h1t-hrs?tab=followers"><img src="https://img.shields.io/github/followers/h4r5h1t-hrs?style=social"></a>
<a href="https://github.com/h4r5h1t-hrs/webcopilot/issues"><img src="https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat"></a>
<a href="https://github.com/h4r5h1t-hrs/webcopilot/blob/master/LICENSE"><img src="https://img.shields.io/badge/License-MIT-yellow.svg"></a>
<a href="#"><img src="https://img.shields.io/badge/Made%20with-Bash-1f425f.svg"></a>
<a href="#"><img src="https://madewithlove.org.in/badge.svg"></a>
</p>

<p align="center">
  <a href="#features">Features</a> •
  <a href="#installing-webCopilot">Installation</a> •
  <a href="#usage">Usage</a> •
  <a href="#running-webcopilot">WebCopilot</a> •
  <a href="#tools-used">Tools Used</a> •
  <a href="#acknowledgement">Acknowledgement</a>
</p>

---

**WebCopilot** is an automation tool designed to enumerate subdomains of the target and detect bugs using different open-source tools.

The script first enumerate all the subdomains of the given target domain using assetfinder, sublister, subfinder, amass, findomain, hackertarget, riddler and crt then do active subdomain enumeration using SecLists wordlist then filters out all the live subdomains using dnsx then it extract titles of the subdomains using httpx & scans for subdomain takeover using subjack. Then it uses gauplus & waybackurls to crawl all the endpoints of the given subdomains then it use gf patterns to filters out xss, lfi, ssrf, sqli, open redirect & rce parameters from that given subdomains, and then it scans for vulnerabilities on the subdomains using different open-source tools (like kxss, dalfox, openredirex, nuclei, etc.). Then it'll print out the result of the scan and save all the output in a specified directory. 

# Features

- Subdomain Enumeration using [assetfinder](https://github.com/tomnomnom/assetfinder), [sublist3r](https://github.com/aboul3la/Sublist3r), [subfinder](https://github.com/projectdiscovery/subfinder), [amass](https://github.com/OWASP/Amass), [findomain](https://github.com/Findomain/Findomain), etc.
- Active Subdomain Enumeration usign [SecLists/DNS](https://github.com/danielmiessler/SecLists/tree/master/Discovery/DNS) wordlist.
- Extract titles and take screenshots of live subdoamins using [aquatone](https://github.com/michenriksen/aquatone) & [httpx](https://github.com/projectdiscovery/httpx).
- Crawl all the endpoints using [waybackurls](https://github.com/tomnomnom/waybackurls) & [gauplus](https://github.com/bp0lr/gauplus).
- Filter out XSS, SQLi, LFI, SSRF, Open redirecct, etc parameters
- Run different open-source tools on these parameters


# Usage
```bash
g!2m0:~ webcopilot -h
```

```js
             
                                ──────▄▀▄─────▄▀▄
                                ─────▄█░░▀▀▀▀▀░░█▄
                                ─▄▄──█░░░░░░░░░░░█──▄▄
                                █▄▄█─█░░▀░░┬░░▀░░█─█▄▄█
 ██╗░░░░░░░██╗███████╗██████╗░░█████╗░░█████╗░██████╗░██╗██╗░░░░░░█████╗░████████╗
░██║░░██╗░░██║██╔════╝██╔══██╗██╔══██╗██╔══██╗██╔══██╗██║██║░░░░░██╔══██╗╚══██╔══╝
░╚██╗████╗██╔╝█████╗░░██████╦╝██║░░╚═╝██║░░██║██████╔╝██║██║░░░░░██║░░██║░░░██║░░░
░░████╔═████║░██╔══╝░░██╔══██╗██║░░██╗██║░░██║██╔═══╝░██║██║░░░░░██║░░██║░░░██║░░░
░░╚██╔╝░╚██╔╝░███████╗██████╦╝╚█████╔╝╚█████╔╝██║░░░░░██║███████╗╚█████╔╝░░░██║░░░
░░░╚═╝░░░╚═╝░░╚══════╝╚═════╝░░╚════╝░░╚════╝░╚═╝░░░░░╚═╝╚══════╝░╚════╝░░░░╚═╝░░░
                                                      [●] @h4r5h1t.hrs | G!2m0

Usage:
webcopilot -d <target>
webcopilot -d <target> -s
webcopilot [-d target] [-o output destination] [-t threads] [-b blind server URL] [-x exclude domains]

Flags:  
  -d        Add your target [Requried]
  -o        To save outputs in folder [Default: domain.com]
  -t        Number of threads [Default: 100]
  -b        Add your server for BXSS [Default: False]
  -x        Exclude out of scope domains [Default: False]
  -s        Run only Subdomain Enumeration [Default: False]
  -h        Show this help message

Example: webcopilot  -d domain.com -o domain -t 333 -x exclude.txt -b testServer.xss
Use https://xsshunter.com/ or https://interact.projectdiscovery.io/ to get your server
```
# Installing WebCopilot

WebCopilot requires **git** to install successfully. Run the following command as a **root** to install webcopilot 

```bash
git clone https://github.com/h4r5h1t-hrs/webcopilot && cd webcopilot/ && chmod +x webcopilot install.sh && mv webcopilot /usr/bin/ && ./install.sh
```
### Tools Used:

<p align="center">
<a href="https://github.com/projectdiscovery/subfinder">SubFinder</a> • 
<a href="https://github.com/aboul3la/Sublist3r">Sublist3r</a> •
<a href="https://github.com/Findomain/Findomain">Findomain</a> •
<a href="https://github.com/tomnomnom/gf">gf</a> •
<a href="https://github.com/devanshbatham/OpenRedireX">OpenRedireX</a> •
<a href="https://github.com/projectdiscovery/dnsx">dnsx</a> •
<a href="https://github.com/tomnomnom/assetfinder">assetfinder</a> •
<a href="https://github.com/projectdiscovery/httpx">httpx</a> •
<a href="https://github.com/Emoe/kxss">kxss</a> •
<a href="https://github.com/tomnomnom/qsreplace">qsreplace</a> •
<a href="https://github.com/projectdiscovery/nuclei">Nuclei</a> •
<a href="https://github.com/hahwul/dalfox">dalfox</a> •
<a href="https://github.com/tomnomnom/anew">anew</a> •
<a href="https://github.com/stedolan/jq">jq</a> •
<a href="https://github.com/michenriksen/aquatone">aquatone</a> •
<a href="https://github.com/ameenmaali/urldedupe">urldedupe</a> •
<a href="https://github.com/OWASP/Amass">Amass</a> •
<a href="https://github.com/bp0lr/gauplus">gauplus</a> •
<a href="https://github.com/tomnomnom/waybackurls">waybackurls</a> •
<a href="https://github.com/dwisiswant0/crlfuzz">crlfuzz</a>
</p>

## Running WebCopilot
To run the tool on a target, just use the following command.
```bash
g!2m0:~ webcopilot -d bugcrowd.com
```
The `-o` command can be used to specify an output dir.
```bash
g!2m0:~ webcopilot -d bugcrowd.com -o bugcrowd
```
The `-s` command can be used for only subdomain enumerations (Active + Passive and also get title & screenshots).
```bash
g!2m0:~ webcopilot -d bugcrowd.com -o bugcrowd -s 
```
The `-t` command can be used to add thrads to your scan for faster result.
```bash
g!2m0:~ webcopilot -d bugcrowd.com -o bugcrowd -t 333 
```
The `-b` command can be used for blind xss (OOB), you can get your server from [xsshunter](https://xsshunter.com/) or [interact](https://interact.projectdiscovery.io/)
```bash 
g!2m0:~ webcopilot -d bugcrowd.com -o bugcrowd -t 333 -b testServer.xss
```
The `-x` command can be used to exclude out of scope domains.
```bash
g!2m0:~ echo out.bugcrowd.com > excludeDomain.txt
g!2m0:~ webcopilot -d bugcrowd.com -o bugcrowd -t 333 -x excludeDomain.txt -b testServer.xss
```
---

```js
g!2m0:~ webcopilot -d bugcrowd.com - bugcrowd



                                ──────▄▀▄─────▄▀▄
                                ─────▄█░░▀▀▀▀▀░░█▄
                                ─▄▄──█░░░░░░░░░░░█──▄▄
                                █▄▄█─█░░▀░░┬░░▀░░█─█▄▄█
 ██╗░░░░░░░██╗███████╗██████╗░░█████╗░░█████╗░██████╗░██╗██╗░░░░░░█████╗░████████╗
░██║░░██╗░░██║██╔════╝██╔══██╗██╔══██╗██╔══██╗██╔══██╗██║██║░░░░░██╔══██╗╚══██╔══╝
░╚██╗████╗██╔╝█████╗░░██████╦╝██║░░╚═╝██║░░██║██████╔╝██║██║░░░░░██║░░██║░░░██║░░░
░░████╔═████║░██╔══╝░░██╔══██╗██║░░██╗██║░░██║██╔═══╝░██║██║░░░░░██║░░██║░░░██║░░░
░░╚██╔╝░╚██╔╝░███████╗██████╦╝╚█████╔╝╚█████╔╝██║░░░░░██║███████╗╚█████╔╝░░░██║░░░
░░░╚═╝░░░╚═╝░░╚══════╝╚═════╝░░╚════╝░░╚════╝░╚═╝░░░░░╚═╝╚══════╝░╚════╝░░░░╚═╝░░░
                                                      [●] @h4r5h1t.hrs | G!2m0


[❌] Warning: Use with caution. You are responsible for your own actions.
[❌] Developers assume no liability and are not responsible for any misuse or damage cause by this tool.


Target:  bugcrowd.com
Output:  /home/gizmo/targets/bugcrowd
Threads: 100
Server:  False
Exclude: False
Mode:    Running all Enumeration
Time:    30-08-2021 15:10:00

[!] Please wait while scanning...

[●] Subdoamin Scanning is in progress: Scanning subdomains of bugcrowd.com
[●] Subdoamin Scanned  -  [assetfinder✔]                 Subdomain Found: 34
[●] Subdoamin Scanned  -  [sublist3r✔]                   Subdomain Found: 29
[●] Subdoamin Scanned  -  [subfinder✔]                   Subdomain Found: 54
[●] Subdoamin Scanned  -  [amass✔]                       Subdomain Found: 43
[●] Subdoamin Scanned  -  [findomain✔]                   Subdomain Found: 27

[●] Active Subdoamin Scanning is in progress:
[!] Please be patient. This may take a while...
[●] Active Subdoamin Scanned  -  [ffuf✔]                 Subdomain Found: 0
[●] Active Subdoamin Scanned  -  [amass✔]                Subdomain Found: 0

[●] Subdomain Scanning: Filtering out of scope subdomains
[●] Subdomain Scanning: Filtering Alive subdomains
[●] Subdomain Scanning: Getting titles of valid subdomains
[●] Visual inspection of Subdoamins is completed.        Check: /subdomains/aquatone/

[●] Scanning Completed for Subdomains of bugcrowd.com    Total: 43 | Alive: 30

[●] Endpoints Scanning Completed for Subdomains of bugcrowd.com  Total: 11032
[●] Vulnerabilities Scanning is in progress: Getting all vulnerabilities of bugcrowd.com
[●] Vulnerabilities Scanned  -  [XSS✔]                   Found: 0
[●] Vulnerabilities Scanned  -  [SQLi✔]                  Found: 0
[●] Vulnerabilities Scanned  -  [LFI✔]                   Found: 0
[●] Vulnerabilities Scanned  -  [CRLF✔]                  Found: 0
[●] Vulnerabilities Scanned  -  [SSRF✔]                  Found: 0
[●] Vulnerabilities Scanned  -  [Sensitive Data✔]        Found: 0
[●] Vulnerabilities Scanned  -  [Open redirect✔]         Found: 0
[●] Vulnerabilities Scanned  -  [Subdomain Takeover✔]    Found: 0
[●] Vulnerabilities Scanned  -  [Nuclie✔]                Found: 0
[●] Vulnerabilities Scanning Completed for Subdomains of bugcrowd.com    Check: /vulnerabilities/


▒█▀▀█ █▀▀ █▀▀ █░░█ █░░ ▀▀█▀▀
▒█▄▄▀ █▀▀ ▀▀█ █░░█ █░░ ░░█░░
▒█░▒█ ▀▀▀ ▀▀▀ ░▀▀▀ ▀▀▀ ░░▀░░

[+] Subdomains of bugcrowd.com
[+] Subdomains Found: 0
[+] Subdomains Alive: 0
[+] Endpoints: 11032
[+] XSS: 0
[+] SQLi: 0
[+] Open Redirect: 0
[+] SSRF: 0
[+] CRLF: 0
[+] LFI: 0
[+] Sensitive Data: 0
[+] Subdomain Takeover: 0
[+] Nuclei: 0

```
---

### Acknowledgement
WebCopilot is inspired from [Garud](https://github.com/R0X4R/Garud) & [Pinaak](https://github.com/R0X4R/Pinaak) by [ROX4R](https://github.com/R0X4R/).  

#### Thanks to the authors of the tools & wordlists used in this script.

[@aboul3la](https://github.com/aboul3la) [@tomnomnom](https://github.com/tomnomnom) [@lc](https://github.com/lc) [@hahwul](https://github.com/hahwul) [@projectdiscovery](https://github.com/projectdiscovery) [@maurosoria](https://github.com/maurosoria) [@shelld3v](https://github.com/shelld3v) [@devanshbatham](https://github.com/devanshbatham) [@michenriksen](https://github.com/michenriksen) [@defparam](https://github.com/defparam/) [@projectdiscovery](https://github.com/projectdiscovery) [@bp0lr](https://github.com/bp0lr/) [@ameenmaali](https://github.com/ameenmaali) [@dwisiswant0](https://github.com/dwisiswant0) [@OWASP](https://github.com/OWASP/) [Edu4rdSHL](https://github.com/Edu4rdSHL) [danielmiessler](https://github.com/danielmiessler) [@1ndianl33t](https://github.com/1ndianl33t) [ROX4R](https://github.com/R0X4R/)

<table>
<td>
<b>Warning:</b> Developers assume no liability and are not responsible for any misuse or damage cause by this tool. So, please se with caution because you are responsible for your own actions.
</td>
</table>
