# try-racket

## Setup

### Requirements

* You need [Racket] since this is a Racket application.
* You need [node] and [nvm] to build the assets.

### First-time Setup

    $ nvm use && npm install && npm run build
    $ raco pkg install chief
    $ raco pkg install try-racket/ try-racket-tests/  # install and build the application and its deps

### Development environment

Copy `.env.default` to `.env`.  [chief] will automatically load the
variables defined in this file into the environment of the
subprocesses defined in the `Procfile` whenever it is run.

The app expects to be run behind an SSL terminated connection (for
example, behind an nginx instance using a self-signed cert), even for
local development .  You can disable this requirement by setting
`current-continuation-key-cookie-secure?` parameter to `#f` before the
application is started.

## Running the app locally

    $ nvm use
    $ raco chief start

## License

    try-racket is licensed under the 3-Clause BSD license.

[Postgres]: https://www.postgresql.org/
[Racket]: https://racket-lang.org/
[argon2]: https://www.argon2.com/
[chief]: https://github.com/Bogdanp/racket-chief
[node]: https://nodejs.org/en/
[nvm]: https://github.com/nvm-sh/nvm
