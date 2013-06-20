# /usr/bin/env: node: No such file or directory

- slug: usr-bin-env-node-no-such-file-or-directory
- date: 2012-11-18
- source: https://github.com/joyent/node/issues/3911
- category: tech
- tags: gnu-linux, www-dev, node, js

--------------------------

If running npm commands gives you the following error `"/usr/bin/env: node: No such file or directory"`,
try to use  the following command to fix it:

````bash
sudo ln -s /usr/bin/nodejs /usr/bin/node
````