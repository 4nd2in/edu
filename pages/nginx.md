# nginx (engine x)
	- NGINX is an HTTP web server, reverse proxy, content cache, load balancer, [[TCP]]/[[UDP]] proxy server and mail proxy server.
	- ## Structure
	  collapsed:: true
		- nginx consists of modules which are controlled by directives (name and parameters separeted by spaces and ends with a semicolon) specified in the configuration file (`/etc/nginx/nginx.conf`).
		- A directive can also be a block (surrounded by braces)
		- If a block directive can have other directives inside braces, it is called a context (like `server`)
		- Directives placed outside any contexts are considered to be in the `main` context
	- ## Serving file content
	  collapsed:: true
		- Whenever a request is made, nginx decides which `server` processes a request- It tests the specified URI against the parameters of the `location` directives defined inside the `server` block.
		- ```nginx
		  server {
		    location / {
		      root /data/www;
		    }
		  }
		  ```
		- This `location` block specifies the `/` prefix compared with the URI from the request. For matching requests, the URI will be added to the path specified in the root directive, that is , to `/var/www`, to form the path to the requested file on the local file system.
		- > If there are several matching `location` blocks nginx selects the one with the longest prefix.
	- ## Proxy
		- One of the frequent uses of nginx is setting it up as a proxy server, which means a server that receives requests, passes them to the proxied servers, retrieves responses from them, and sends them to the clients.
		- ```nginx
		  server {
		    location / {
		        proxy_pass http://localhost:80
		    }
		  }
		  ```
		-
	-
- Source
	- https://nginx.org/en/docs
- Tags
	- #computer-science