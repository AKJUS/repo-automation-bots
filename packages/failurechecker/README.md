# ⛔️ DEPRECATED : Failure Checker Bot

This bot is deprecated and is planned for shutdown August 5, 2025.

---

Cron task that periodically checks client libraries for failed releases.

Instructions are provided in [googleapis/repo-automation-bots](https://github.com/googleapis/repo-automation-bots/blob/main/README.md) for deploying and testing your bots.

This bot uses nock for mocking requests to GitHub, and snap-shot-it for capturing responses; This allows updates to the API surface to be treated as a visual diff, rather than tediously asserting against each field.

## Running tests:

`npm run test`

### To update snapshots:

`npm run test:snap`

## Contributing

If you have suggestions for how failurechecker could be improved, or want to report a bug, open an issue! We'd love all and any contributions.

For more, check out the Contributing Guide.

## License

Apache 2.0 © 2019 Google LLC.