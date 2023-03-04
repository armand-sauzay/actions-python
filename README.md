<p align="center">
  <a href="https://armand-sauzay.github.io/actions-python/"><img src="docs/docs/logo.svg" alt="Actions Python" width="700" height="100"></a>
</p>

<p align="center">
    <b align="center">
        This project is forked from open-turo/actions-python
    </b>
    <p align="center">
    GitHub Action for `python` based repositories. It uses `pip` as package manager.
    </p>
</p>

<p align="center">
    <a href="https://github.com/armand-sauzay/actions-python/actions/workflows/ci.yaml">
        <img src="https://github.com/armand-sauzay/actions-python/actions/workflows/ci.yaml/badge.svg" alt="CI">
    </a>
    <a href="https://github.com/armand-sauzay/actions-python/actions/workflows/release.yaml">
        <img src="https://github.com/armand-sauzay/actions-python/actions/workflows/release.yaml/badge.svg?branch=main" alt="Release">
    </a>
    <a href="https://github.com/armand-sauzay/actions-python/releases">
        <img src="https://img.shields.io/github/v/tag/armand-sauzay/actions-python?sort=semver" alt="Version">
    </a>
</p>

---

**Documentation**: <a href="https://armand-sauzay.github.io/actions-python">https://armand-sauzay.github.io/actions-python/</a>

**Source Code**: <a href="https://github.com/armand-sauzay/actions-python">https://github.com/armand-sauzay/actions-python</a>

---

## Actions

### action: [`lint`](./lint)

Lint will run pre-commit linters against the consumer repository, optionally checking out to to the consumer repository.

See usage [here](./lint/README.md#usage).

Documentation is found [here](./lint/README.md).

### action: [`test`](./test)

Test will run tests in the consumer repository using [pytest](https://github.com/pytest-dev/pytest). This action will also check out the repository if `checkout-repo` is passed, as well as `pip install .[dev]` and `pip install .[test]` for dependencies.

See usage [here](./test/README.md#usage).

Documentation is found [here](./test/README.md).

### action: [`release`](./release)

Release will optionally checkout the consumer repository and attempt a [Semantic Release](https://semantic-release.gitbook.io/semantic-release/usage/configuration) using the root level configuration file (e.g. .releaserc.json) indicating branches and plugins to use to facilitate the release.

See usage [here](./release/README.md#usage).

Documentation is found [here](./release/README.md).

## Get Help

Each Action has a detailed README for how to use it as referenced above. Please review Issues, post new Issues against this repository as needed.
