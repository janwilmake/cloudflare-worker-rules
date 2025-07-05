It's interesting to me that cloudflare has these very complex rulesets system but it's not really integrated with workers. Worker assets have `_redirects` and `_headers` which can be very useful but don't have dynamic capabilities.

The capabilities of rulesets is much more vast, and the advantage, just like `_redirects`, `_headers`, and regular assets, is that your worker doesn't get hit, saving you money, since assets are served with free egress.

Imagine we'd build in something like this:

https://letmeprompt.com/previous-prompt-ht-j7r3k20

Preferably we'd have a single overarching `rules.json` which has a JSON Schema that allows us to pass redirects, headers, and dynamic rules like the above.

This repo contains an initial draft of such a rules.json schema, with a draft implementation of how we can make this work using an extension to wrangler.

Context:

https://developers.cloudflare.com/workers/static-assets/headers/index.md
https://developers.cloudflare.com/workers/static-assets/redirects/index.md
