# docker-firefox-headless

> Docker images for running a headless Firefox browser

No-nonsense Docker image for running Firefox headless.

The original use case for this project was to let Karma run JavaScript unit tests in headless browsers in Docker.

## Use a Prebuilt Image

```bash
$ docker run -it rkuzsma/firefox-headless-stable:latest firefox \
  -p headless \
  -no-remote \
  -headless \
  -url http://example.com
```

## Build an Image Locally

```bash
$ export FIREFOX_VERSION=63.0.1
$ docker build -t firefox-headless:$FIREFOX_VERSION \
  --build-arg FIREFOX_VERSION=$FIREFOX_VERSION .
```

Set `FIREFOX_VERSION` to any of the release versions at https://download-installer.cdn.mozilla.net/pub/firefox/releases/ or set it to `latest` to build an image using the latest nightly Firefox build.

## Run a Locally Built Image

Firefox:
```bash
$ docker run -it firefox-headless:63.0.1 firefox \
  -p headless \
  -no-remote \
  -headless \
  -url http://example.com
```
