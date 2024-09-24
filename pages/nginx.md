# nginx (engine x)
	- NGINX is an HTTP web server, reverse proxy, content cache, load balancer, [[TCP]]/[[UDP]] proxy server and mail proxy server.
	- ## Structure
	  collapsed:: true
		- nginx consists of modules which are controlled by directives (name and parameters separeted by spaces and ends with a semicolon) specified in the configuration file (`/etc/nginx/nginx.conf`).
		- A directive can also be a block (surrounded by braces)
		- If a block directive can have other directives inside braces, it is called a context (like `server`)
		- Directives placed outside any contexts are considered to be in the `main` context
	- ## Core Module
	  id:: 66f2b38b-a8e3-4b85-9b15-090efab67ea4
		- Whenever a request is made, nginx decides which `server` processes a request- It tests the specified URI against the parameters of the `location` directives defined inside the `server` block.
		- ```nginx
		  server {
		    listen 8080;
		    
		    location / {
		      root /data/www;
		    }
		    
		    location /images {
		      root /data;
		    }
		  }
		  ```
		- This `location` block specifies the `/` prefix compared with the URI from the request. For matching requests, the URI will be added to the path specified in the root directive, that is , to `/var/www`, to form the path to the requested file on the local file system.
		- > If there are several matching `location` blocks nginx selects the one with the longest prefix.
	- ## Proxy module
		- ### Basic
		  collapsed:: true
			- One of the frequent uses of nginx is setting it up as a proxy server, which means a server that receives requests, passes them to the proxied servers, retrieves responses from them, and sends them to the clients.
			- ```nginx
			  server {
			    location / {
			        proxy_pass http://localhost:8080
			    }
			    
			    location ~ \.(gif|jpg|png)$ {
			      root /data/images;
			    }
			  }
			  ```
			- This server (separate from the one above) will filter requests ending with `.gif`, `.jpg` or `.png` and map them to the `/data/images` directory and pass all other requests to the proxied server configured in ((66f2b38b-a8e3-4b85-9b15-090efab67ea4)).
		- ### Headers
		  collapsed:: true
			- By default, nginx redefines two header fields in procied requests, `Host (set to $proxy_host)` and `Connection (set to close)` and eliminates the header fields whose values are empty strings.
			- To change these setting, as well as modify other header fields, `proxy_set_header` directive can be used.
		- ### Compression
		  collapsed:: true
			- Compressing responses often significantly reduces the size of transmitted data. However, since compression happens at runtime it can also add considerable processing overhead which can negatively affect performance. NGINX performs compression before sending responses to clients, but does not “double compress” responses that are already compressed (for example, by a proxied server).
			- Compression can be enabled with `gzip on;`
			- By default only `text/html` responses are compressed. To add more MIME types, use `gzip_types <MIME type> <MIME type>`.
			- To specify the minimum length of the response to compress, use the `gzip_min_length` directive. The default is 20 bytes.
			-
	- ### HTTP map module
	-
	-
- Source
	- https://nginx.org/en/docs
- Tags
	- #computer-science