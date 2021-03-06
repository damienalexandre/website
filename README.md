# AFSY Website

AFSY stands for "Association Francophone des utilisateurs de Symfony".
See http://afsy.fr/ for more informations.

## How to add your own events on the website?

First you need to contact one of the administrators with your email and sensiolabs connect id: you may fill an issue to contact one of them.

Then, you will be able to log in into the Afsy website Back Office: http://afsy.fr/admin/. You can register new Articles and Authors.
When your article is done and published, spread the world on social networks!

## Install and run

If you want to test the current version (which requires php 7.3) :

```bash
$ composer install
$ docker-compose up -d
$ symfony php bin/console doctrine:migrations:load
$ symfony php bin/console doctrine:fixtures:load
$ symfony serve
```

## Howto update CSS styles
---------------------------------------------------
    1. Install compass

        sudo gem install compass

    2. Run Compass

        compass watch

## Deployments

Deployments are made using [Fabric](https://get.fabric.io/), using a simple
basic script.

 * copy `bin/fabfile.py-dist` to `bin/fabfile.py`
 * set the preprod and prod SSh servers and paths
 * ensure Fabric is installed on your system
 * run the following command:

```sh
$ fab -f bin/fabfile.py -R preprod deploy
```

This will deploy the `master` branch in the `preprod` env, run composer
install, clear the cache and warmup it.
