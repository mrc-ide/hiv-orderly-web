## hiv-orderly OrderlyWeb configuration

### Prerequisites

First, install the deploy tool

```
pip3 install --user orderly-web
```

Ensure that the path that the script is copied into is in your path (on Linux, most likely `~/.local/bin`, on OSX `~/Library/Python/<version>/bin`

### Start

```
orderly-web start config
```

### Upgrading

It is possible that the `orderly-web` deploy scripts should be updated

```
pip3 install --user --upgrade orderly-web
```

Then redeploy with:

```
orderly-web stop config
orderly-web start --pull config
```
