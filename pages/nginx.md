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
	  collapsed:: true
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
	  collapsed:: true
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
	- ## HTTP map module
	  collapsed:: true
		- The `map` creates a new variable whose value depends on values of one or more of the source variables specified in the first parameter.
		- The `default` parameter sets the resulting value if the source value matches none of the specified variants. When default is not specified, the default resulting value will be an empty string.
	- ## Stream module
	  collapsed:: true
		- This is a core NGINX module that provides essential features for handling and proxying [[TCP]] and [[UDP]] traffic. It was introduced to extend nginx's ability to proxy not just HTTP traffic, but also raw streams such as database connections, email protocols and custom TCP/UDP applications.
		- With this nginx can proxy [[SSL]]/ [[TLS]] connections for stream protocols, allowing it to terminate SSL for applications like VPNs or secure database connections.
		- This adds support for [[SSL]]/[[TLS]] preread, which enabled nginx to inspect the initial `ClientHello` message of a TLS handshake without terminating the SSL session. This is useful for directing encrypted traffic based on the [SNI]( ((66f2bf22-3fb6-47aa-adbe-9edfa362ce6b)) ) field in TLS, allowing for functionalities like SNI-based routing.
- Source
	- https://nginx.org/en/docs
- Tags
	- #computer-science