参考： https://github.com/verdaccio/verdaccio/tree/master/docker-examples/v5/reverse_proxy/nginx_relative 少量调整，完成SSL部署， 注意以下中文部分

# Nginx Relative Path with Verdaccio 5

This example runs two verdaccio versions:

- Running `verdaccio:5.x` http://localhost/verdaccio/

Note: we should add more sort of configurations here.

**Nginx HTTP Example**

```bash
docker compose up --build --force-recreate
```

open the browser

```
http://localhost/relative_path/
```

**Nginx SSL Example**

 - 拷贝`ssl`证书到`nginx_ssl`下， 名字保持和`nginx-default.conf`文件里设置一致，
 - 修改 `nginx-default.conf`,改域名设置

```bash
docker compose -f docker-compose_ssl.yml up --build --force-recreate
```

open the browser

```
https://yourdomain/verdaccio/
```
