# .commitlintrc.yaml

In order to use commitlint, you need to install it first. See
[commitlint](https://commitlint.js.org/#/) for more information.

You then have to add the following configuration to your `.commitlintrc.yaml`
file, in order to use the [conventional
commit](https://www.conventionalcommits.org/en/v1.0.0/) convention:

```yaml
extends:
  - "@commitlint/config-conventional"
```
