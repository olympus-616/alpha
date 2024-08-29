hermes-cli
=================

CLI Access to Olympus-616


[![oclif](https://img.shields.io/badge/cli-oclif-brightgreen.svg)](https://oclif.io)
[![Version](https://img.shields.io/npm/v/hermes-cli.svg)](https://npmjs.org/package/hermes-cli)
[![Downloads/week](https://img.shields.io/npm/dw/hermes-cli.svg)](https://npmjs.org/package/hermes-cli)


<!-- toc -->
* [Usage](#usage)
* [Commands](#commands)
<!-- tocstop -->
# Usage
<!-- usage -->
```sh-session
$ npm install -g hermes-cli
$ hermes COMMAND
running command...
$ hermes (--version)
hermes-cli/0.0.0 win32-x64 node-v22.7.0
$ hermes --help [COMMAND]
USAGE
  $ hermes COMMAND
...
```
<!-- usagestop -->
# Commands
<!-- commands -->
* [`hermes hello PERSON`](#hermes-hello-person)
* [`hermes hello world`](#hermes-hello-world)
* [`hermes help [COMMAND]`](#hermes-help-command)
* [`hermes plugins`](#hermes-plugins)
* [`hermes plugins add PLUGIN`](#hermes-plugins-add-plugin)
* [`hermes plugins:inspect PLUGIN...`](#hermes-pluginsinspect-plugin)
* [`hermes plugins install PLUGIN`](#hermes-plugins-install-plugin)
* [`hermes plugins link PATH`](#hermes-plugins-link-path)
* [`hermes plugins remove [PLUGIN]`](#hermes-plugins-remove-plugin)
* [`hermes plugins reset`](#hermes-plugins-reset)
* [`hermes plugins uninstall [PLUGIN]`](#hermes-plugins-uninstall-plugin)
* [`hermes plugins unlink [PLUGIN]`](#hermes-plugins-unlink-plugin)
* [`hermes plugins update`](#hermes-plugins-update)

## `hermes hello PERSON`

Say hello

```
USAGE
  $ hermes hello PERSON -f <value>

ARGUMENTS
  PERSON  Person to say hello to

FLAGS
  -f, --from=<value>  (required) Who is saying hello

DESCRIPTION
  Say hello

EXAMPLES
  $ hermes hello friend --from oclif
  hello friend from oclif! (./src/commands/hello/index.ts)
```

_See code: [src/commands/hello/index.ts](https://github.com/olympus-616/hermes-cli/blob/v0.0.0/src/commands/hello/index.ts)_

## `hermes hello world`

Say hello world

```
USAGE
  $ hermes hello world

DESCRIPTION
  Say hello world

EXAMPLES
  $ hermes hello world
  hello world! (./src/commands/hello/world.ts)
```

_See code: [src/commands/hello/world.ts](https://github.com/olympus-616/hermes-cli/blob/v0.0.0/src/commands/hello/world.ts)_

## `hermes help [COMMAND]`

Display help for hermes.

```
USAGE
  $ hermes help [COMMAND...] [-n]

ARGUMENTS
  COMMAND...  Command to show help for.

FLAGS
  -n, --nested-commands  Include all nested commands in the output.

DESCRIPTION
  Display help for hermes.
```

_See code: [@oclif/plugin-help](https://github.com/oclif/plugin-help/blob/v6.2.10/src/commands/help.ts)_

## `hermes plugins`

List installed plugins.

```
USAGE
  $ hermes plugins [--json] [--core]

FLAGS
  --core  Show core plugins.

GLOBAL FLAGS
  --json  Format output as json.

DESCRIPTION
  List installed plugins.

EXAMPLES
  $ hermes plugins
```

_See code: [@oclif/plugin-plugins](https://github.com/oclif/plugin-plugins/blob/v5.4.6/src/commands/plugins/index.ts)_

## `hermes plugins add PLUGIN`

Installs a plugin into hermes.

```
USAGE
  $ hermes plugins add PLUGIN... [--json] [-f] [-h] [-s | -v]

ARGUMENTS
  PLUGIN...  Plugin to install.

FLAGS
  -f, --force    Force npm to fetch remote resources even if a local copy exists on disk.
  -h, --help     Show CLI help.
  -s, --silent   Silences npm output.
  -v, --verbose  Show verbose npm output.

GLOBAL FLAGS
  --json  Format output as json.

DESCRIPTION
  Installs a plugin into hermes.

  Uses npm to install plugins.

  Installation of a user-installed plugin will override a core plugin.

  Use the HERMES_NPM_LOG_LEVEL environment variable to set the npm loglevel.
  Use the HERMES_NPM_REGISTRY environment variable to set the npm registry.

ALIASES
  $ hermes plugins add

EXAMPLES
  Install a plugin from npm registry.

    $ hermes plugins add myplugin

  Install a plugin from a github url.

    $ hermes plugins add https://github.com/someuser/someplugin

  Install a plugin from a github slug.

    $ hermes plugins add someuser/someplugin
```

## `hermes plugins:inspect PLUGIN...`

Displays installation properties of a plugin.

```
USAGE
  $ hermes plugins inspect PLUGIN...

ARGUMENTS
  PLUGIN...  [default: .] Plugin to inspect.

FLAGS
  -h, --help     Show CLI help.
  -v, --verbose

GLOBAL FLAGS
  --json  Format output as json.

DESCRIPTION
  Displays installation properties of a plugin.

EXAMPLES
  $ hermes plugins inspect myplugin
```

_See code: [@oclif/plugin-plugins](https://github.com/oclif/plugin-plugins/blob/v5.4.6/src/commands/plugins/inspect.ts)_

## `hermes plugins install PLUGIN`

Installs a plugin into hermes.

```
USAGE
  $ hermes plugins install PLUGIN... [--json] [-f] [-h] [-s | -v]

ARGUMENTS
  PLUGIN...  Plugin to install.

FLAGS
  -f, --force    Force npm to fetch remote resources even if a local copy exists on disk.
  -h, --help     Show CLI help.
  -s, --silent   Silences npm output.
  -v, --verbose  Show verbose npm output.

GLOBAL FLAGS
  --json  Format output as json.

DESCRIPTION
  Installs a plugin into hermes.

  Uses npm to install plugins.

  Installation of a user-installed plugin will override a core plugin.

  Use the HERMES_NPM_LOG_LEVEL environment variable to set the npm loglevel.
  Use the HERMES_NPM_REGISTRY environment variable to set the npm registry.

ALIASES
  $ hermes plugins add

EXAMPLES
  Install a plugin from npm registry.

    $ hermes plugins install myplugin

  Install a plugin from a github url.

    $ hermes plugins install https://github.com/someuser/someplugin

  Install a plugin from a github slug.

    $ hermes plugins install someuser/someplugin
```

_See code: [@oclif/plugin-plugins](https://github.com/oclif/plugin-plugins/blob/v5.4.6/src/commands/plugins/install.ts)_

## `hermes plugins link PATH`

Links a plugin into the CLI for development.

```
USAGE
  $ hermes plugins link PATH [-h] [--install] [-v]

ARGUMENTS
  PATH  [default: .] path to plugin

FLAGS
  -h, --help          Show CLI help.
  -v, --verbose
      --[no-]install  Install dependencies after linking the plugin.

DESCRIPTION
  Links a plugin into the CLI for development.
  Installation of a linked plugin will override a user-installed or core plugin.

  e.g. If you have a user-installed or core plugin that has a 'hello' command, installing a linked plugin with a 'hello'
  command will override the user-installed or core plugin implementation. This is useful for development work.


EXAMPLES
  $ hermes plugins link myplugin
```

_See code: [@oclif/plugin-plugins](https://github.com/oclif/plugin-plugins/blob/v5.4.6/src/commands/plugins/link.ts)_

## `hermes plugins remove [PLUGIN]`

Removes a plugin from the CLI.

```
USAGE
  $ hermes plugins remove [PLUGIN...] [-h] [-v]

ARGUMENTS
  PLUGIN...  plugin to uninstall

FLAGS
  -h, --help     Show CLI help.
  -v, --verbose

DESCRIPTION
  Removes a plugin from the CLI.

ALIASES
  $ hermes plugins unlink
  $ hermes plugins remove

EXAMPLES
  $ hermes plugins remove myplugin
```

## `hermes plugins reset`

Remove all user-installed and linked plugins.

```
USAGE
  $ hermes plugins reset [--hard] [--reinstall]

FLAGS
  --hard       Delete node_modules and package manager related files in addition to uninstalling plugins.
  --reinstall  Reinstall all plugins after uninstalling.
```

_See code: [@oclif/plugin-plugins](https://github.com/oclif/plugin-plugins/blob/v5.4.6/src/commands/plugins/reset.ts)_

## `hermes plugins uninstall [PLUGIN]`

Removes a plugin from the CLI.

```
USAGE
  $ hermes plugins uninstall [PLUGIN...] [-h] [-v]

ARGUMENTS
  PLUGIN...  plugin to uninstall

FLAGS
  -h, --help     Show CLI help.
  -v, --verbose

DESCRIPTION
  Removes a plugin from the CLI.

ALIASES
  $ hermes plugins unlink
  $ hermes plugins remove

EXAMPLES
  $ hermes plugins uninstall myplugin
```

_See code: [@oclif/plugin-plugins](https://github.com/oclif/plugin-plugins/blob/v5.4.6/src/commands/plugins/uninstall.ts)_

## `hermes plugins unlink [PLUGIN]`

Removes a plugin from the CLI.

```
USAGE
  $ hermes plugins unlink [PLUGIN...] [-h] [-v]

ARGUMENTS
  PLUGIN...  plugin to uninstall

FLAGS
  -h, --help     Show CLI help.
  -v, --verbose

DESCRIPTION
  Removes a plugin from the CLI.

ALIASES
  $ hermes plugins unlink
  $ hermes plugins remove

EXAMPLES
  $ hermes plugins unlink myplugin
```

## `hermes plugins update`

Update installed plugins.

```
USAGE
  $ hermes plugins update [-h] [-v]

FLAGS
  -h, --help     Show CLI help.
  -v, --verbose

DESCRIPTION
  Update installed plugins.
```

_See code: [@oclif/plugin-plugins](https://github.com/oclif/plugin-plugins/blob/v5.4.6/src/commands/plugins/update.ts)_
<!-- commandsstop -->
