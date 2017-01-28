# cent7puptest

This is a simple Docker image for running Puppet tests. When you start the
container you will need to have it run `/bin/bundle install`. By default it
will install the latest version of Puppet 4. You can override this by passing
an environment variable (see below). You can also supplement this with other
environment variables.

## Suggested variables

* `-e PUPPET_VERSION="~> 3.0"`
* `-e PUPPET_VERSION="~> 3.0" -e FUTURE_PARSER="yes"`
* `-e PUPPET_VERSION="~> 4.0" -e STRICT_VARIABLES="yes"`

## Example usage

```bash
$ docker run -it --name cent7puptest-v3 -e PUPPET_VERSION="~> 3.0" cent7puptest /bin/bash

$ docker run -it --name cent7puptest-v3-future -e PUPPET_VERSION="~> 3.0" -e FUTURE_PARSER="yes" cent7puptest /bin/bash

$ docker run -it --name cent7puptest-v4 -e PUPPET_VERSION="~> 4.0" -e STRICT_VARIABLES="yes" cent7puptest /bin/bash
```
