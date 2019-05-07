---
layout: page
title: How to reserve an ENS .eth name
permalink: /howto/
---

First, check that your request meets the [eligibility requirements](../about/).

Next, create a DNS TXT record on the domain you wish to use. Records must be on the domain `_ens.yourname.tld`. The record should be of the format `a=0x12345...`, specifying the address you wish to have control of the ENS domain.

For example, if your domain is 'fooeth.com', you want to claim `foo.eth`, and your account address is `0x6090a6e47849629b7245dfa1ca21d94cd15878ef`, you should create a TXT record on `_ens.fooeth.com`, with the contents `a=0x6090a6e47849629b7245dfa1ca21d94cd15878ef`.

Finally, [create a new file](https://github.com/ensdomains/name-reservations/new/master/_reservations) in the ensdomains/name-reservations repository, with the following contents:

```
---
name: [requested domain]
site: [your site]
owner: "[your Ethereum address]""
contact: [your email]
---
```

Note that the owner field *must* be in quotes.

The contact field is optional; specify an email address if you want to be contacted with news about your name reservation.

Name this file after the DNS domain you are making the claim based on, with a suffix of `.md`.

For example, with the above example of `fooeth.com`, you would create a file called `fooeth.com.md`:

```
---
name: foo
site: fooeth.com
owner: "0x6090a6e47849629b7245dfa1ca21d94cd15878ef"
contact: admin@fooeth.com
---
```

Finally, submit a pull request, by selecting the "Create a new branch for this commit and start a pull request" option at the bottom of the page.

If your submission meets all the criteria, your pull request will be merged and your request will be added to the repository.

Note that having your request merged does *not* guarantee ownership of the domain you requested; conflicts are solved based on the oldest name making a claim.
