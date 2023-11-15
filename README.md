# gandi-update

A small and simple bash script to update IP addresses on [Gandi.net](https://www.gandi.net) using the [LiveDNS API](https://api.gandi.net/docs/livedns/) of Gandi. The script only needs `curl`, `coreutils` and a `host` (preferably from `bind9-host` package) command.

First, set correct variables (`RECORD` for the dns record to update, `DOMAIN` for the main domain and `APIKEY` for the api key) in `/etc/default/gandi-update`. Then place the script under `/usr/local/bin` and  run the script as a cronjob or as systemd timer.

Enter following line to run script every five minutes in a cronjob:

`*/5 * * * * /usr/local/bin/gandi-update`

Copy `gandi-update.service` and `gandi-update.timer` to `/etc/systemd/system/` and activate the timer with:

`systemctl enable --now gandi-update.timer`
