# Akamai

## Akamai Pragma Headers

Sends a request with the Pragma header set to extract Akamai property defined variables and values. Among these variable there could be juicy information like the origin server hostname or hardcoded tokens, credentials, etc.

## Akamai Staging Edgehost Lookup

Performs a DNS lookup to resolve the IP of the Akamai staging Edge Server hostname. The staging hostname is obtained by adding the string "-staging" before the TLD. Ex: `example.com.edgekey.net` -> `example.com.edgekey-staging.net`. After mapping locally the staging edge server IP to the target (add an entry to `/etc/hosts`), you could try a scan with the `akamai/akamai-pragma-headers.yaml` template to check if some variables are disclosed in the staging network.