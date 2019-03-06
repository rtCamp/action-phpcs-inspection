# PHPCS Inspections - GitHub Action

A [GitHub Action](https://github.com/features/actions) that can be used to run PHPCS inspections on the diff of patch being commited.

## Installation

To use this GitHub Action, you must have access to GitHub Actions. GitHub Actions are currently only available in public beta (you must [apply for access](https://github.com/features/actions)).

1. Create a `.github/main.workflow` in your GitHub repo.
2. Add the following code to the `main.workflow` file and commit it to the repo's `master` branch.

```bash
workflow "PHPCS Inspections" {
  resolves = ["Run phpcs inspection"]
  on = "push"
}

action "Run phpcs inspection" {
  uses = "rtCamp/rtCamp/action-phpcs-inspection@master"
  env = {
    DIFF_BASE="master"
  }
}

```

## Environment Variables

```shell
# To compare the committed changes between master and the current branch. Default: origin/master.
DIFF_BASE=master

# Head commit from which diff will be taken. Default: `git rev-parse HEAD`
DIFF_HEAD=0fbe5466e1ec4eecb4bf0c7453ee4fa045ef3ebf
```

## License

[MIT](LICENSE) © 2019 rtCamp
