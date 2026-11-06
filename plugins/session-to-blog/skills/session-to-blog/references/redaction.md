# Redaction checklist

Go through every line of the draft, including code blocks, tables, image alt text and frontmatter. A post is public and permanent: caches and archives keep it after you delete it.

## Never in a post

- [ ] **Credentials of any kind:** passwords, tokens, API keys, cookie values, session IDs. Not even their *shape* (`sk-...`, a 32-character hex string). Replace with `<redacted>` or a made-up placeholder that looks nothing like the real format.
- [ ] **Infrastructure:**
  - server hostnames, IP addresses, SSH aliases
  - server paths (`/opt/...`, `/srv/...`, `/home/<user>/...`) and local paths with a username in them
  - port numbers and port schemes
  - container, service, volume and database names
  - internal URLs, admin URLs, staging URLs
- [ ] **Open security work:** anything still unfixed, on any site or tenant. Write that post once it is fixed everywhere, and say so in the post. A write-up of a fix that one deployment is still missing is a map to that deployment.
- [ ] **How the system is wired:** network boundaries, which part forwards which credential, how a protected service checks its callers, the order checks run in, and how a check could be bypassed by someone with access. Tell the lesson ("the database was reachable from outside"), not the route to it. A security post names the class of problem and the fix.
- [ ] **People:** names, emails or handles of anyone but the owner, unless they agreed. Clients, testers and colleagues become "a client", "a tester". Use they/them when pronouns aren't known.
- [ ] **Customer or user data:** orders, messages, analytics numbers that could identify anyone.
- [ ] **Private business details:** pricing, contracts, unreleased plans, private repo names the owner hasn't made public.

## Fine to include

- The owner's own **public** sites, products and games, by name and with a link. Check that the link is public first.
- Short code excerpts from the owner's own projects.
- Generic config patterns, with values made up.
- Commit-free descriptions of what a fix did ("the list now only returns live pages to anonymous callers").

## The mosaic

Each post can be harmless on its own while all of them together describe the whole setup: the services, which one guards which, how deploys and checks work. Before handing over, ask what this post adds to what earlier posts already told, and drop the details only an attacker needs.

## Last pass

- [ ] Search the draft for `/opt`, `/Users`, `/home`, `localhost`, `:` followed by four or five digits, `@`, `password`, `token`, `key`, `secret`.
- [ ] Read the outro and alternatives once more: they are where specifics tend to slip back in.
