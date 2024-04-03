# Drupal Docker Compose

This is a repository that has working drupal docker compose. 
All tools have been installed into phpfpm image.
Everything can be done inside docker images, no need to install any drupal/php tools in to the host machine.

I've built this ontop of Digital Ocean's instructions:
[How To Install Drupal with Docker Compose](https://www.digitalocean.com/community/tutorials/how-to-install-drupal-with-docker-compose)

# How to use this image

## Configuration

When running the image, the default configuration is stored in /docker/*. Everything should work out of the box, but you might want to go over all configuration.

## docker-compose

Running:

```console
$ docker compose up -d
```
