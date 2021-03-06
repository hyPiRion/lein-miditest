# lein-miditest
[![Build Status](https://secure.travis-ci.org/hyPiRion/lein-miditest.png?branch=master "Build Status")](http://travis-ci.org/hyPiRion/lein-miditest)

A Leiningen plugin to play a midi tone when tests and retests have finished.

## Usage

Since this little plugin only adds midi tones to the `test` and `retest` tasks,
there's not much to do except setting it up. As I assume that you would like to
add tones to all tests ran with Leiningen: Put `[lein-miditest "0.1.0"]` in the
`:plugins` vector inside your `:user` profile within `~/.lein/profiles.clj`
should do what you want.

If you've never modified the `~/.lein/profiles.clj` file before, create it and
put the following clojure snippet into it:

```clj
{:user
 {:plugins [[lein-miditest "0.1.0"]]}}
```

If you want to put this into a `project.clj`, every single contributor will have
midi sounds playing whenever they test code with Leiningen. If you want a midi
choir, so be it, but take it into consideration if you want contributors.
`lein-miditest` may also crash servers and CI services (because of a lack of
sound systems), so be a bit careful.

That should be everything. `lein-miditest` comes with the task `miditest`, which
would check if the midi system works correctly on your machine: It should play
the french horn and just exit. 

Now you can continue to use `lein test` and `lein retest` as you'd usually do,
but with the sound of a timpani whenever all test succeeds, and the french horn
when one or more fails.

## Compatibility

`lein-miditest` has been developed and tested on a 64-bit Debian Jessie laptop
and desktop, with 64-bit OpenJDK 1.6 and 1.7 and Leiningen 2.x. It seems to work
without issues on such a setup.

If you have trouble getting it up and working, please create a Github issue with
your operating system, Java version (`java -version`) and Leiningen version
(`lein version`).

## License

Copyright © 2013 by Jean Niklas L'orange.

Distributed under the [Eclipse Public License, version 1.0][license]. You can
find a copy in the root of this repository with the name `LICENSE`.

[license]: http://www.eclipse.org/legal/epl-v10.html "Eclipse Public License, version 1.0"
