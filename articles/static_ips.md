New Proxy Support:

Many users have expressed a desire to be able to whitelist Blitline postback IP addresses for security reasons.
While we can have hundreds of machines joining and leaving our cloud clusters, we could not guarantee what IP addresses
our actual machines would be posting back from. So to address this, we have added a new "use_proxy" : true option which will
send all postbacks through one of our proxy machines, thus ensuring that the IP addresses are always one of our listed IP addresses.

If you need to whitelist postback calls, you MUST have the following set on your Blitline JSON submissions:

1. You must set a "v"ersion larger than 1.19 (1.22 is current latest version)
2. You must set "use_proxy" on the base JSON node.
3. You obviously must have a "postback_url" defined for us to post back to.

The IP addresses which we proxy through are the following:

Blitline Proxies:
52.70.222.55
52.72.65.98
52.4.244.159

You must whitelist ALL 3 addresses.

When "use_proxy" : true is set, all postbacks will come through 1 of the 3 IP addresses listed above.


