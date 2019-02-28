# How to setup registry docker container, a docker registry service

* Please copy the .env.example to .env and edit the values before running docker-compose up.
* To setup the htpasswd run the following on the host:
  * docker exec --it *registry_registry_#* sh
    * htpassword -Bbn *Username* '*password*' > /auth/htpasswd
  * Restart the container stack