Put the module files in following directory:

[ec2-user@ip-172-31-40-183 testModule]$ pwd

/home/ec2-user/nginx/testModule

[ec2-user@ip-172-31-40-183 testModule]$ ls

config  ngx_http_hello_module.c


Put nginx source code in following directory:

[ec2-user@ip-172-31-40-183 nginx-1.17.5]$ pwd

/home/ec2-user/nginx/nginx-1.17.5


Then configure, make, make install:

./configure --with-http_ssl_module --add-module=/home/ec2-user/nginx/testModule

make

sudo make install


In /usr/local/nginx/conf/nginx.conf, add following configure:

```
	location / {
		hello 'Hello World';
	}
```

Then restart nginx:

sudo ./nginx -t

sudo ./nginx -s stop

sudo ./nginx

Access following url:

https://ec2-3-84-156-249.compute-1.amazonaws.com/


this module has been built and tested successfully with nginx-1.17.5

install development suite:

sudo yum groupinstall "Development Tools"























