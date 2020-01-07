```
server {
  listen              443 ssl;
  server_name         www.example.com;
  ssl_certificate     /path/to/1.crt;
  ssl_certificate_key /path/to/2.key;
  ssl_protocols       TLSv1 TLSv1.1 TLSv1.2;
  ssl_ciphers         HIGH:!aNULL:!MD5;

  #charset koi8-r;

  #access_log  logs/host.access.log  main;

  location / {
    proxy_pass http://127.0.0.1:3000;
  }

  #error_page  404              /404.html;

  # redirect server error pages to the static page /50x.html
  #
  error_page   500 502 503 504  /50x.html;
  location = /50x.html {
    root   html;
  }
}
```