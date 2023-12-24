# Mochify.js

> Headless browser testing for Mocha with plugins for Puppeteer, Playwright,
> WebDriver and JSDom.

## Install

This will install the Mochify CLI and the puppeteer driver in your current
project and add it to the `devDependencies`:

```
npm i @mochify/cli @mochify/driver-puppeteer -D
```

[Puppeteer][] will download a recent version of Chromium. If you want to skip
the download and provide your own executable instead, define the
`PUPPETEER_SKIP_CHROMIUM_DOWNLOAD` environment variable or add this to your
`package.json`:

```json
{
  "config": {
    "puppeteer_skip_chromium_download": true
  }
}
```

For proxy settings and other environment variables, see the [Puppeteer
documentation][puppeteer-envs].

## Usage

```bash
mochify --driver puppeteer './{,!(node_modules)/**}/*.test.js'
```

## Workaround for Apple Silicon

Puppeteer fails to launch on M1. Follow these steps to work around:

- Install Google Chrome
- Define these environment variables:

  ```bash
  export PUPPETEER_SKIP_CHROMIUM_DOWNLOAD=true
  export PUPPETEER_EXECUTABLE_PATH=/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome
  ```

## License

MIT

[puppeteer]: https://github.com/GoogleChrome/puppeteer
[puppeteer-envs]: https://github.com/GoogleChrome/puppeteer/blob/master/docs/api.md#environment-variables
