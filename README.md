# How to setup registry docker container, a docker registry service

* Please copy the .env.example to .env and edit the values before running docker-compose up.
* To setup the htpasswd run the following on the host:
  * docker exec --it *registry_registry_#* sh
    * htpassword -Bbn *Username* '*password*' > /auth/htpasswd
  * Restart the container stack

## Login with Self-Signed SSL cert

* Create the follow folders if they are missing on the client (**must be root to write these folders and files**)
  * /etc/docker/certs.d/*server-name*:*port*
* Copy the .crt file into /etc/docker/certs.d/*server-name*:*port*
  * rsync -azv *user*@*server*:/*folder*/*to*/*cert*.crt .
  * sudo cp -la *cert*.crt /etc/docker/certs.d/*server-name*:*port*/
    * This will copy the cert file from your server to the current directory and then create a hard-link copy to docker certs