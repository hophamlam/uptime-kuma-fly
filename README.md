# Personal Uptime Kuma server

## Create a 1Gb volume for uptime-kuma

```bash
fly volumes create hophamlam_uptimekuma_vol --region sin --size 1
```

Paste the volume name to [mount] part in `fly.toml`. Example:

```toml
[mounts]
  destination = "/app/data"
  source = "hophamlam_uptimekuma_vol"
```

```bash
flyctl deploy
```

## Add custom domain

Change into your domain + Use CNAME to point your domain to auto-generated fly.clio app url

```bash
flyctl certs create status.mydomain.com
```

Do the same with `www.status.mydomain.com`

Reference:

> https://noted.lol/easy-off-site-monitoring-with-fly-io-and-uptime-kuma/
