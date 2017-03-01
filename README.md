# Vagrant + Ubuntu LTS + Ansible + Nginx Proxy Server + Static Content Cache + SSL  

## This is a sample repo created by Gonzalo Arce. No external roles or playbooks were used. Everything was set up from scratch for demonstration purposes.
1 - Clone This Repository

2 - Run "vagrant up" from your command line (just make sure you have Vagrant installed in your host). 

3 - That's it! Nothing else is needed, you don't need to have Ansible set up on your local host. Worry-less out-of-the-box solution!

## Test (HTTP)

Access the proxy server via http://localhost:8080 from your local browser (make sure you don't have port 8080 binded to something else).

## Test (HTTPS)

HTTPS implementation is only added as a simple testing purpose. As Self signed certificates were used, please ignore the security
warning. Access the https proxy server via https://localhost:8443 from your local browser (make sure you don't have port 8443 binded to something else). No redirection was implemented at this point, however it could be added later on.

## Test Cache features

- Change the value of the var "proxied_host" in vars/main.yml, to another website URL, to better test static content caching.
- re-provision by running:

```bash
$ vagrant provision 
```
## Then:

### From a local commandline, run:

```bash
$ curl -X GET -I localhost:8080
```

### And verify static content was cached, by looking at the headers, like in this example:

```bash
"X-Proxy-Cache: HIT"
```


I hope you enjoy it!

- This is tested to work out of the box and my aim was to deliver it Today, there is still room for enhancements and polishing, feel free to discuss further.


- Gonzalo



