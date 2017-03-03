---
layout: post
title: "Easy get your home external IP"
date: 2017-03-03 11:49:25 +0700
comments: true
categories:
_published: false
---

To get your external IP:

```sh
curl api.ipify.org
123.123.123.123
```

Script to update IP:

```sh
ip=$(curl api.ipify.org)
touch 'current.ip'
current=$(cat current.ip)

if [ "$ip" != "$current" ]; then
  curl -X POST -H 'Content-type: application/json' --data "{\"text\":\"$ip\"}" url_to_Slack_app_integration
  echo "$ip" > 'current.ip'
fi
```

Add script to cron:

```sh
sudo chmod +x myip.sh
crontab -e

15 * * * * path_to_script_file
```

Done!
