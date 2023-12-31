# gandi-update

A small, even minimalistic, yet simple and posix compliant shell script to update IP addresses on [Gandi.net](https://www.gandi.net) using the [LiveDNS API](https://api.gandi.net/docs/livedns/) of Gandi. The script only needs `curl` and `find` command. With a working `sendmail` command, the script sends a notification mail on errors.

First, copy `gandi-update.sample` to `/etc/default/gandi-update` and set correct variables (`RECORD` for the resource record to update, `DOMAIN` for the main domain and `APIKEY` for the api key). Then place the script under `/usr/local/bin` and run it as a cronjob or as systemd timer.

Enter following line to run the script every five minutes as a cronjob:

`*/5 * * * * /usr/local/bin/gandi-update`

Or copy `gandi-update.service` and `gandi-update.timer` to `/etc/systemd/system/` and activate the timer with:

`systemctl enable --now gandi-update.timer`
