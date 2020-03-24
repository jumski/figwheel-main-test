# figwheel-main-test

Created to test integration with vim-fireplace and other stuff.

## Development with vim-fireplace

Start regular repl:

```
lein repl
```

Run this in regular repl:

```clojure
(require 'figwheel.main.api)
(figwheel.main.api/start {:mode :serve} "dev")
(figwheel.main.api/cljs-repl "dev")
```

Test if cljs repl is connected to browser:

```
(js/alert "I'm working!!!")
```

If alert pops up, you are good. Start vim, open cljs file and run following:

```
:Piggieback (figwheel.main.api/repl-env "dev")
```

Now, put this in the file:

```clojure
(js/alert "I'm working from vim!!!")
```

And eval it with `cpp`.  If alert pops up, you are good to go!

## Development

To get an interactive development environment run:

    lein fig:build

This will auto compile and send all changes to the browser without the
need to reload. After the compilation process is complete, you will
get a Browser Connected REPL. An easy way to try it is:

    (js/alert "Am I connected?")

and you should see an alert in the browser window.

To clean all compiled files:

	lein clean

To create a production build run:

	lein clean
	lein fig:min


## License

Copyright © 2018 FIXME

Distributed under the Eclipse Public License either version 1.0 or (at your option) any later version.
