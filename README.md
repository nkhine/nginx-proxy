Build Instructions
----
<pre>
// pull latest jwilder/nginx-proxy
docker pull jwilder/nginx-proxy:latest

// following command will build image with tag 'nkhine/nginx-proxy'
docker build -t nkhine/nginx-proxy .

// sample launch command - better refer to docker/README.md for updated command.
docker run -d --restart always --name nginx-proxy-server \
   --publish 80:80 \
   --publish 443:443 \
   --volume /ccc/certs:/etc/nginx/certs:ro \
   --volume /var/run/docker.sock:/tmp/docker.sock:ro \
   --volume /ccc/docker/00_redirect.conf:/etc/nginx/conf.d/00_redirect.conf \
   nkhine/nginx-proxy
</pre>