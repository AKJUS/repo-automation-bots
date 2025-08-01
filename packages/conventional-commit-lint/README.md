# ⛔️ DEPRECATED : conventional-commit-lint

This bot is deprecated and is planned for shutdown August 13, 2025.

We suggest looking into a supported GitHub actions implementation. You can find a few options: https://github.com/marketplace?query=commitlint&type=actions

---

> A GitHub App built with [Probot](https://github.com/probot/probot) that lints commit messages based on conventionalcommits.org

## Setup

```sh
# Install dependencies
npm install

# Run the bot
npm start
```

## Configuration

The following configuration settings can be set by creating a
`.github/conventional-commit-lint.yaml` file:

| Name                  | Description                                   | Default              |
|-----------------------|-----------------------------------------------|----------------------|
| enabled               | Should commit linting be enabled?             | `boolean` = `true`   |
| always_check_pr_title | If set to true, the bot will use the PR title | `boolean` = `false`  |

## Testing

This bot uses [nock](https://www.npmjs.com/package/nock) for mocking requests
to GitHub, and [snap-shot-it](https://www.npmjs.com/package/snap-shot-it) for capturing
responses; This allows updates to the API surface to be treated as a visual diff,
rather than tediously asserting against each field.

Running tests:

```sh
npm run test
```

To update snapshots:

```sh
npm run test:snap
```

## Contributing

If you have suggestions for how conventional-commit-lint could be improved, or want to report a bug, open an issue! We'd love all and any contributions.

For more, check out the [Contributing Guide](../../CONTRIBUTING.md).

## License

Apache 2.0 © 2019 Google Inc.

