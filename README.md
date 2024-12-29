A Github action to automatically rerun PR Checks when they fail due to rate limits.

Use it like this:
```yaml
name: Autorerun

on:
  workflow_dispatch:
  schedule:
    - cron: '0 0 * * *' # TODO when to run

jobs:
  bump:
    runs-on: ubuntu-latest
    steps:
      - uses: plengauer/autorerun@main # TODO pin to a version if needed
        with:
          github_token: ${{ secrets.MY_GITHUB_TOKEN }} # token for GITHUB to retrigger, needs permissions to run GitHub Actions
```
