# Liners_bounty
UMA SÉRIE DE ONELINERS PARA BUG BOUNTY

[Blog do Eike](https://ei7hacker.blogspot.com/)

[HTTPX](https://github.com/projectdiscovery/httpx)

[SUBFINDER](https://github.com/projectdiscovery/subfinder)

[HTTPROBE](https://github.com/tomnomnom/httprobe)

[ASSETFINDER](https://github.com/tomnomnom/assetfinder)
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
