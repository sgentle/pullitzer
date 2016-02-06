Pullitzer
=========

Dead-simple GitHub repo updates.

Usage
-----

```
$ npm install -g pullitzer
$ pullitzer --example-config
$ vim example.config.json
$ pullitzer --config example.config.json
```

Then add the URL to your GitHub project's webhooks page.

How it works
------------

Pullitzer runs as a webhook server for GitHub. Whenever it receives a ping, it will fetch (or clone) any remotes attached to that repo. It can also optionally pull those updates into the work tree and run a command whenever it does this. Useful for automatically updating services on GitHub updates!

Everything is configurable in the `config.json`, which you can see in the source, or generate by using the `--example-config` command.


Security & webhook secrets
--------------------------

Make sure to set your webhook secret to something random. The webhook secret is used to authenticate requests as genuinely coming from GitHub. If that secret is guessable, someone could flood your pullitzer instance with fake requests and DoS the machine it's on.