A fork of : https://hotio.dev/pullio

This fork modifies the `generic` webhook in pullio to work with Rocket.Chat webhooks

Installation:

```
sudo curl -fsSL "https://raw.githubusercontent.com/adatamonk/pullioRC/master/pullio.sh" -o /usr/local/bin/pullio
sudo chmod +x /usr/local/bin/pullio
```

Usage:

Add the following lines to the `labels` for each application you want to update
```
      - "org.hotio.pullio.notify=true"
      - "org.hotio.pullio.update=true"
      - "org.hotio.pullio.generic.webhook=https://chat.domain.com/hooks/abcd/abcd"
```

and then setup a cron job

```
0 8 * * * /usr/local/bin/pullio
```

To customize the webhook output look at line 96 in `pullio.sh`
