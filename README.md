# Quilt test GitHub Action

This repo contains a [GitHub Action](https://github.com/features/actions) that you can use to run [Quilt’s `test` command](https://github.com/lemonmade/quilt/blob/main/documentation/features/testing.md) on your repo. This action will checkout the repo, install your dependencies, and run Quilt’s `test` command.

To use this action, create a [new workflow](https://docs.github.com/en/actions/quickstart#creating-your-first-workflow), and include this repo’s action as one of the steps:

```yml
name: CI
on: [push]
jobs:
  test:
    name: Test 🧪
    runs-on: ubuntu-latest
    steps:
      - uses: quilt-framework/action-test@v1
        name: Test
```
