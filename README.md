## hiv-orderly OrderlyWeb configuration

### Prerequisites

First, install the deploy tool

```
pip3 install --user orderly-web
```

Ensure that the path that the script is copied into is in your path (on Linux, most likely `~/.local/bin`, on OSX `~/Library/Python/<version>/bin`

### Start

```
./start (all | <instance>..)
```

To start all instances

```
./start all
```

To start a specific instance

```
./start naomi
```

Notes
* The name needs to match the dir name in this repo, so for inference data it is `inference_data`
* The `naomi` instance starts the proxy which proxies all other instances at `hiv-orderly.dide.ic.ac.uk/<instance>`. When other instances are brought up we connect them to the proxy, because of this if you restart the `naomi` instance you must restart all other instances so they can connect to the new proxy.


### Stop

```
./stop (all | <instance>...)
```

### Upgrading

```
./stop (all | <instance>..)
./start (all | <instance>..)
```

Note that if you restart the `naomi` instance all other instances need to be restarted so they can be added to the proxy configuration.

### Install a package

```
./orderly_install <instance> 'command'
```

e.g.

```
./orderly_install fertility "install.packages(\"dplyr\")"
```

### Start an R session in the orderly container

```
./orderly_r <instance>
```

You can use this to then run things like `orderly_pull_dependencies` or `orderly_pull_archive`
