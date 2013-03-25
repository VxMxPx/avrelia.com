# Felix Felicis Basic Commands

- slug: felix-felicis-basic-commands
- source: http://liquidluck.readthedocs.org/en/latest/
- date: 2013-03-25
- tags: www-dev

-------------------------------------

## Installation and Setup

Install `liquidluck` (Felix Felicis) and `tornado` (if need preview server) through `pip`:

	pip install liquidluck
	pip install tornado

Initialize new project:

	liquidluck init

Create post:

	nano content/hello-world.md

Run testing server (if you installed tornado):

	liquidluck server

## Writing

Common meta (I've added `source`, which I'm accessing in temple with `{{post.source}}`:

	# Felix Felicis Basic Commands

	- slug: felix-felicis-basic-commands
	- source: http://liquidluck.readthedocs.org/en/latest/
	- date: 2013-03-25
	- tags: www-dev

## Webhook

Felix Felicis supports webhook, when you push to GitHub (or BitBucket), your blog can generate itself.

	liquidluck webhook start -p 9876

On GitHub head over to your blog source repo admin and select Service Hooks,
add url in following format:

	http://ip_address:port/webhook