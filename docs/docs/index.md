# Actions Python

** This project is forked from open-turo/actions-python **

GitHub Action for `python` based repositories. It uses `pip` as package manager.

[![Release](https://img.shields.io/github/v/release/armand-sauzay/actions-python)](https://github.com/armand-sauzay/actions-python/releases/)
[![Tests pass/fail](https://img.shields.io/github/workflow/status/armand-sauzay/actions-python/CI)](https://github.com/armand-sauzay/actions-python/actions/)
[![License](https://img.shields.io/github/license/armand-sauzay/actions-python)](./LICENSE)
[![Contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)](https://github.com/dwyl/esta/issues)
[![semantic-release: angular](https://img.shields.io/badge/semantic--release-angular-e10079?logo=semantic-release)](https://github.com/semantic-release/semantic-release)
[![Conventional commits](https://img.shields.io/badge/conventional%20commits-1.0.2-%23FE5196?logo=conventionalcommits&logoColor=white)](https://conventionalcommits.org)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

## Actions

### action: [`lint`](./lint)

Lint will run pre-commit linters against the consumer repository, optionally checking out to to the consumer repository.

See usage [here](./lint/#usage).

Documentation is found [here](./lint).

### action: [`test`](./test)

Test will run tests in the consumer repository using [pytest](https://github.com/pytest-dev/pytest). This action will also check out the repository if `checkout-repo` is passed, as well as `pip install .[dev]` and `pip install .[test]` for dependencies.

See usage [here](./test#usage).

Documentation is found [here](./test).

### action: [`release`](./release)

Release will optionally checkout the consumer repository and attempt a [Semantic Release](https://semantic-release.gitbook.io/semantic-release/usage/configuration) using the root level configuration file (e.g. .releaserc.json) indicating branches and plugins to use to facilitate the release.

See usage [here](./release#usage).

Documentation is found [here](./release).

## Get Help

Each Action has a detailed README for how to use it as referenced above. Please review Issues, post new Issues against this repository as needed.
