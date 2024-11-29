# Introduction

This repository contains source for [Queens Law public website](https://www.qclm.edu.np)

# Tech stack
1. Domain provided by register.mos.com.np
2. DNS by Cloudflare
3. Website contents from Github.com

## Development Setup
* Knowledge of [Jekyll](https://jekyllrb.com/), version 4.2.2 currently used
* Install [docker](https://www.docker.com/)
* Use docker image from [https://github.com/envygeeks/jekyll-docker](https://github.com/envygeeks/jekyll-docker)
* Run docker container to build and generate static files 

```bash
$ cd website
$ export JEKYLL_VERSION=4.2.2
$ docker run --rm \
  --volume="$PWD:/srv/jekyll:Z" \
  --volume="$PWD/vendor/bundle:/usr/local/bundle:Z" \
  -it jekyll/jekyll:$JEKYLL_VERSION \
  jekyll build --watch
```

It will generate static file in `_site` under project root directory.

## Test website locally

```bash
$ cd website 
$ cd _site
$ npx http-server -c 1 .
```

Then browse to `http://localhost:8080` to view the new changes

# Deployment

Once everything looks good on development. Push changes to `gh-pages` branch.

`gh-pages` is configured to deploy to `qclm.edu.np` using Github actions.


