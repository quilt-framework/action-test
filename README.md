# Quilt test GitHub Action

This repo contains a [GitHub Action](https://github.com/features/actions) that you can use to run [Quilt’s `test` command](https://github.com/lemonmade/quilt/blob/main/documentation/features/testing.md) on your repo. This action will run Quilt’s `test` command, and will save any caches created by testing tools for subsequent runs.

To use this action, create a [new workflow](https://docs.github.com/en/actions/quickstart#creating-your-first-workflow), and include this repo’s action as one of the steps. Note that this action does not checkout your repo or install your dependencies, so you need to make sure you do this yourself, or use the [`quilt-framework/action-prepare`](https://github.com/quilt-framework/action-prepare) GitHub action to set up a standard Quilt workspace:

```yml
name: CI
on: [push]
jobs:
  test:
    name: Test 🧪
    runs-on: ubuntu-latest
    steps:
      - uses: quilt-framework/action-prepare@v1
      - uses: quilt-framework/action-test@v2
```

You can pass custom arguments to the lint command by providing an `arguments` input to this GitHub action:

```yml
name: CI
on: [push]
jobs:
  test:
    name: Test 🧪
    runs-on: ubuntu-latest
    steps:
      - uses: quilt-framework/action-prepare@v1
      - uses: quilt-framework/action-test@v2
        with:
          arguments: '--exclude-pattern e2e'
```
