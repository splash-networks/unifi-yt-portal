# Ubiquiti External Captive Portal

The following actions are required to use the code given in this repo:

Note: the following instructions assume that your site ID is `default`. In case of a different site ID rename the `default` folder according to the site ID. For example, if the site ID is `rig5vxr7` then `default` should be renamed to `rig5vxr7`.

## Portal Setup Using Git

Suppose your domain is `hotspot.example.com`. It can be setup like this:

```
cd /var/www
mkdir -p hotspot.example.com/guest/
git clone https://github.com/splash-networks/unifi-yt-portal
mv unifi-yt-portal hotspot.example.com/guest/s
cd hotspot.example.com/guest/s
```

Copy the `.env.example` file to `.env` and set the values of the given environment variables in it:

```
cp .env.example .env
nano .env
```

Navigate to public folder:

`cd hotspot.example.com/guest/s/default`

Use [this](https://getcomposer.org/download/) link to install Composer. Then run `php composer.phar install` to install the packages given in `composer.json`.

## Apache Virtual Hosts

Apache virtual host can be setup on the portal server using the instructions given [here](https://gist.github.com/nasirhafeez/d47c9d68742227a23f1011455a190490#apache-site-setup).

The portal files are in default folder in this repository. DocumentRoot will be:

`/var/www/hotspot.example.com`

It has been successfully tested with `Unifi Network Server v8.2.93`.
