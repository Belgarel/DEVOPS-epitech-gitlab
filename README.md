# DEVOPS-epitech-gitlab
gitlab project for T-NSA-700 (school project)

## Setting up the gitlab server

* *Prerequisite:* Make sure ipv6 is disabled on your debian. [Method on debian 9](https://www.itzgeek.com/how-tos/linux/debian/how-to-disable-ipv6-on-debian-9-ubuntu-16-04.html#Method_1).
* Follow [this tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-gitlab-on-debian-9) to setup the server
* Create a self-signed [SSL certificate](https://support.ssl.com/Knowledgebase/Article/View/19/0/der-vs-crt-vs-cer-vs-pem-certificates-and-how-to-convert-them) and [install it](https://docs.gitlab.com/omnibus/settings/ssl.html#install-custom-public-certificates) (by putting it in the 
  * In `/etc/gitlab.gitlab.rb`: `external_url 'https://gitlab.devops.com'`
  * set `letsencrypt['enabled']` to `false`
  * I joined the certificate I was able to generate. It was not good enough for the runner integration, though :/
* Create a user and init the back and front repositories

## Setting up a gitlab runner

On another server:
* [Install docker](https://docs.docker.com/install/linux/docker-ce/debian/), [install gitlab runner](https://docs.gitlab.com/runner/install/linux-repository.html) and [a docker runner](https://docs.gitlab.com/runner/install/docker.html)
* Run `gitlab-runner register` => I was never able to go further :(

Since I was not able to setup the runner because of those SSL issues, I could not build pipelines.
