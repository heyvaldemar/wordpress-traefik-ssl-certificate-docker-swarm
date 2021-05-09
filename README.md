# WordPress with SSL Certificate in a Docker Swarm

Configure Traefik and create secrets for storing the passwords on the Docker Swarm manager node before applying the configuration.

Traefik configuration: https://github.com/heyValdemar/traefik-ssl-certificate-docker-swarm

Create a secret for storing the password for MySQL root using the command:

`printf "YourPassword" | docker secret create wordpress-mysql-root-password -`

Create a secret for storing the password for WordPress database using the command:

`printf "YourPassword" | docker secret create wordpress-database-password -`

Clear passwords from bash history using the command:

`history -c && history -w`

Deploy WordPress in a Docker Swarm using the command:

`docker stack deploy -c wordpress-traefik-ssl-certificate-docker-swarm.yml wordpress`
