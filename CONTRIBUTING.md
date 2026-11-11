# Contributing

This applies to every public repository in the tissue-systems organization
that doesn't have a CONTRIBUTING.md of its own.

Bug reports and pull requests are welcome. For anything bigger than a small
fix, open an issue first so we can agree on the approach before you spend
time on it. Security problems go to the address in
[SECURITY.md](SECURITY.md), not the issue tracker.

## Reporting a bug

Say which version you're on, your operating system, what you did, what you
expected and what happened instead. The smallest example that shows the
problem is worth more than any log.

## Pull requests

- Keep a pull request to one change. Two unrelated fixes are two pull requests.
- New behaviour comes with a test. A fix comes with a test that fails without
  it.
- CI has to pass. The first time you open a pull request, a maintainer has to
  approve the CI run before it starts, so expect a short wait.
- Pull requests are squash-merged by a maintainer, so the title becomes the
  commit message. Write it the way you'd want to read it in `git log`.
- Dependency updates come from Renovate. Please don't send pull requests that
  only bump versions.

## License

Unless you explicitly state otherwise, any contribution you intentionally
submit for inclusion in a repository is licensed under that repository's
license, without any additional terms or conditions.
