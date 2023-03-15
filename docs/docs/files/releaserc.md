# .releaserc.json

In order to use semantic-release, you need to install it first. See [semantic-release](https://semantic-release.gitbook.io/semantic-release/) for more information.

You then have to add the following configuration to your `.releaserc.json` file, in order to have the following plugins:

```json
{
  "branches": ["main"],
  "plugins": [
    "@semantic-release/commit-analyzer",
    "@semantic-release/release-notes-generator",
    "@semantic-release/github"
  ]
}
```
