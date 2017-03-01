# Vagrant + Ubuntu LTS + Ansible + Proxy Server + Static Content Cache + SSL  

## This is a sample repo created by Gonzalo Arce. 
1 - Clone This Repository

2 - Run "vagrant up" from your command line (vagrant must be installed first)

## Test (HTTP)

Access the proxy server via http://localhost:8080 from your local browser.

## Test (HTTPS)

HTTPS implementation is only added as a simple testing purpose. As Self signed certificates were used, please ignore the security
warning. Access the https proxy server via https://localhost:8443 from your local browser. No redirection was implemented at this point,
and no forced HTTP --> HTTPS either. Please ask if this is required for this challenge purposes.

## Test Cache features

- Change the value of the var "proxied_host" in vars/main.yml, to try the static content caching, by using a different backend website instead of 
the given public API. And re-provision by running "vagrant provision". 

Then:

From a local commandline, run:

$ curl -X GET -I localhost:8080

And verified static content was cached, by looking at the headers, like in this example:

"X-Proxy-Cache: HIT"



I hope you enjoy it!


- Gonzalo



