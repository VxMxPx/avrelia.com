# Useful cURL commands

- slug: useful-curl-commands
- date: 2013-03-27
- tags: gnu-linux, www-dev
- source: https://httpkit.com/resources/HTTP-from-the-Command-Line/ ||
          http://stackoverflow.com/questions/8144777/curl-command-for-issuing-a-post-request ||
          http://www.thegeekstuff.com/2012/04/curl-examples/

-----------------

## Basic Requests

**Get** request

    curl localhost.dev

**Post** request

    curl -X POST localhost.dev

**Put** request

    curl -X PUT -d "" localhost.dev

**Delete** request

    curl -X DELETE localhost.dev

Post request with parameters

    curl -d "username=marko&password=secret" localhost.dev

The above post type is _application/x-www-form-urlencoded_,
for _multipart_ post you can use:

    curl -L username=marko -L password=secret localhost.dev

You can use `-v` to see output including request + response headers,
or `-I` to fetch the HTTP-header only.

## File Handling

Download a Single File

    curl http://localhost/file.txt > file.txt

Fetch Multiple Files at a time

    curl -O url1 -O url2

Continue/Resume a Previous Download

    curl -C - -O http://localhost/file.txt

Limit the Rate of Data Transfer<br>
_The command bellow is limiting the data transfer to 1000 Bytes/second._

    curl --limit-rate 1000B -O http://localhost/file.txt

Download Files from FTP server

    curl -u ftpuser:ftppass -O ftp://ftp_server/public_html/xss.php

## Other

Follow HTTP Location Headers with -L option

    curl -L http://localhost

Set Request Headers

    curl -H "Accept: application/json" \
         -H "Authorization: OAuth 2c3455d1aeffc" \
         http://localhost

Send a Request Body

    curl -X PUT \
         -H 'Content-Type: application/json' \
         -d '{"firstName":"Marko", "lastName":"Gajst"}' \
         http://localhost

Use a File as a Request Body

    curl -X PUT \
         -H 'Content-Type: application/json' \
         -d @example.json \
         http://localhost