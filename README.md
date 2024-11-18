# actions-env-demo
Demoing deploy environment protection rules and mechanisms.

This repo contains [a workflow](.github/workflows/cd.yml) that will run on any `push`, and can also be run manually.

There are two environments configured: `DEV` and `PROD`. 

- `DEV` has no deploy protections.
- `PROD` must be approved before deploys will proceed.
- `PROD` depends on `DEV`. If `DEV` fails, `PROD` will not run.

## Configuration

The two environments were created simply by declaring them in the `cd.yml` workflow file. However, we can't apply the protection rules via the same mechanism.

The Deploy Environment Protection Rules are configured in `Settings -> Environments -> <Env Name>`

From there, you can apply Required Reviewers, Wait Timers, and custom rules.

You can also limit what branches and/or tags are allowed to deploy to an environment.