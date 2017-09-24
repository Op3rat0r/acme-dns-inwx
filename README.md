# ACME-DNS-INWX
Simple helper script for various [Let's Encrypt][1] clients.
Developed for [GetSSL][2], tested with Debian Stretch. Should
work with Ubuntu too.

## Initial setup
Download or clone the archive and extract it to a new folder.

`git clone https://github.com/Op3rat0r/acme-dns-inwx.git`

Copy the example config file `config/.inwx.ini` to `~/.inwx.ini` and
insert your credentials. If enabled, enter your TOTP/2FA shared secret.
Don't forget to check file permissions! (recommended: 0600)

`chmod 0600 ~/.inwx.ini`

Run it for the first time:

```bash
# Add the TXT record _acme-challenge.yourdomain.de
# with value "test" and set TTL to 300 seconds:
./scripts/acme-dns-inwx "yourdomain.de" "test"

# Check your nameserver: (wait some time)
dig TXT "_acme-challenge.yourdomain.de" +short

# Delete the TXT record _acme-challenge.yourdomain.de:
./scripts/acme-dns-inwx --del "yourdomain.de"
```

Take a look at the wiki for more examples.

Important: This project is **not** affiliated with INWX GmbH!

## Important links...
* [Wiki pages](https://github.com/Op3rat0r/acme-dns-inwx/wiki)
* [INWX DNS API](https://www.inwx.com/en/offer/api)
* [Let's Encrypt](https://letsencrypt.org/)

[1]: https://letsencrypt.org/docs/client-options/
[2]: https://github.com/srvrco/getssl
