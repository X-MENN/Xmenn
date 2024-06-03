# GitHub Actions

The Dokku project has an official GitHub Action available on the [GitHub Marketplace](https://github.com/marketplace/actions/dokku). The simplest usage example is as follows:

```yaml
---
name: 'deploy'

on:
  push:
    branches:
      - master

jobs:
  deploy:
    runs-on: ubuntu-22.04
    steps:
      - name: Cloning repo
        uses: actions/checkout@v3
        with:
          fetch-depth: 0

      - name: Push to dokku
        uses: dokku/github-action@master
        with:
          git_remote_url: 'ssh://dokku@dokku.me:22/appname'
          ssh_private_key: ${{ secrets.SSH_PRIVATE_KEY }}
```

For further usage documentation and other advanced examples, see the entry on the [GitHub Marketplace](https://github.com/marketplace/actions/dokku).
