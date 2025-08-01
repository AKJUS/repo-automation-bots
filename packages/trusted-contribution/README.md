# ⛔️ DEPRECATED : trusted-contribution

This bot is deprecated and is planned for shutdown August 6, 2025.

<details>
<summary>
You can replicate trusted-contribution's functionality using GitHub actions
</summary>

```
on:
  pull_request:
    types: [opened, synchronize, reopened]

jobs:
  label:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/github-script@v7
        if: github.actor == '<name-of-actor>'
        with:
          script: |
            github.rest.issues.addLabels({
              owner: context.repo.owner,
              repo: context.repo.repo,
              issue_number: context.payload.pull_request.number,
              labels: ['<label-to-add>']
            })
```
</details>

---

> A GitHub App built with [Probot](https://github.com/probot/probot) that will run Kokoro CI if the PR is created by a trusted contributor.

## Setup

```sh
# Install dependencies
npm install

# Run the bot
npm start
```

### Configuration

To configure the bot, you can create a configuration file:
`.github/trusted-contribution.yml`. The contents of this file allow for the following
options:

| Name                  | Description                                                        | Type       | Default                                                              |
| --------------------- | ------------------------------------------------------------------ | ---------- | -------------------------------------------------------------------- |
| `trustedContributors` | List of user login names that are considered trusted               | `string[]` | `['renovate-bot', 'release-please[bot]', 'gcf-merge-on-green[bot]']` |
| `commentInstructions` | Whether to comment on the PR with instructions for the maintainers | `boolean`  | `false`                                                              |
| `annotations`         | The list of annotation objects to leave the on the PR              | `object`   | `{ type: 'label'; text: 'kokoro:force-run' }`                        |
| `annotation.type`     | Configure the bot to either comment on the PR or add a label       | `comment`  | `label`                                                              |
| `annotation.text`     | The label text or comment text to be left on the PR                | `string`   | `kokoro:force-run`                                                   |

## Deployment and Permissions

### Repository permissions

- metadata - read
- pull requests - read & write

### Organization permissions

- None

### User permissions

- None

## Subscribe to events

- pull request

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

If you have suggestions for how trusted-contribution could be improved, or want to report a bug, open an issue! We'd love all and any contributions.

For more, check out the [Contributing Guide](../../CONTRIBUTING.md).

## License

Apache 2.0 © 2019 Google Inc.
