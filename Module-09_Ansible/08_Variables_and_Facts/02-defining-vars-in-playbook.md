# Defining Variables in Playbook

## Define variables in `vars` section

- The simplest way to define variables is to put a vars section in your
  playbook with the names and values of your variables.

```
vars:
  tls_dir: /etc/nginx/ssl/
  key_file: nginx.key
  cert_file: nginx.crt
  conf_file: /etc/nginx/sites-available/default
  server_name: localhost
```
