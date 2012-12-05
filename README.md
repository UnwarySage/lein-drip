B0;136;0c# lein-drip

A [Leiningen](https://github.com/technomancy/leiningen) plugin which downloads, bootstraps and installs
[drip](https://github.com/flatland/drip) as the default JVM to use for faster
[Leiningen](https://github.com/technomancy/leiningen) startup.

## Clojure-external dependencies

Drip depends on gcc and other tools for self bootstrapping, so you probably
want to ensure you have the normal build-tools installed. On Debian-based
ditros you do it like this:

    $ sudo apt-get install build-essential

## Usage

**Note:** Plugin is only designed to work on Unix-based system. With drip not
having a Windows-version, the plugin is not designed with Windows-portability
in mind.

Put `[lein-drip "0.1.0-SNAPSHOT"]` into the `:plugins` vector of your
profiles.clj (typically found in `~/.lein`) or if you are on
Leiningen 1.x do `lein plugin install lein-drip 0.1.0-SNAPSHOT`.

A minimal profiles.clj should look like this:

    { :user { :plugins [[lein-drip "0.1.0-SNAPSHOT"]]}}

After that execute the following code once, while in a project folder:

    $ lein drip

If something goes wrong and you want to force the process to be run again, you can apply the `force` parameter.
This will also upgrade drip if a new version is avaiable.

    $ lein drip force

## License

Copyright © 2012 Jostein Kjønigsen

Distributed under the Eclipse Public License, the same as Clojure.
