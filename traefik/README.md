# Traefik
I'm using this stack on local, Why ?
One port to remember and after in function of hostname traefik use the right container.

I force traefik container to use the named network `traefik`. All others `docker-compose` will use it.

Traafik read through `docker.sock` containers labels and build frontends and backends. 