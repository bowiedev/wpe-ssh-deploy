# github-action-template

[![Continuous Integration](https://github.com/ergebnis/github-action-template/workflows/Continuous%20Integration/badge.svg)](https://github.com/ergebnis/github-action-template/actions)
[![Continuous Deployment](https://github.com/ergebnis/github-action-template/workflows/Continuous%20Deployment/badge.svg)](https://github.com/ergebnis/github-action-template/actions)

## What does this action do?

:bulb: This is a great place for showing what this action does.

## Usage

Define a workflow in `.github/workflows/continuous-integration.yml` (or add a job if you already have defined workflows).

:bulb: Read more about [Configuring a workflow](https://help.github.com/en/articles/configuring-a-workflow).

```yaml
on:
  pull_request:
  push:
    branches:
      - master
    tags:
      - "**"

name: "Continuous Integration"

jobs:
  github-action-template:
    name: github-action-template

    runs-on: ubuntu-latest

    steps:
      - name: "Checkout"
        uses: actions/checkout@master

      - name: "Run action"
        uses: docker://ergebnis/github-action-template:latest
```

### Docker image

As Docker images are automatically built and pushed on a merge to `master` or when a new tag is created in this repository, the recommended way to use this GitHub action is to reference the pre-built Docker image directly, as seen above.

:bulb: The Docker image can also be executed directly by running

```
$ docker run --interactive --rm --tty --workdir=/app --volume ${PWD}:/app ergebnis/github-action-template:latest
```

For more information, see the [Docker Docs: Docker run reference](https://docs.docker.com/engine/reference/run/).

Instead of using the latest pre-built Docker image, you can also specify a Docker image tag (which corresponds to the tags [released on GitHub](https://github.com/ergebnis/github-action-template/releases)):

```diff
 on:
   pull_request:
   push:
     branches:
       - master
     tags:
       - "**"

 name: "Continuous Integration"

 jobs:
   github-action-template:
     name: github-action-template

     runs-on: ubuntu-latest

     steps:
       - name: "Checkout"
         uses: actions/checkout@master

       - name: "Run action"
-        uses: docker://ergebnis/github-action-template:latest
+        uses: docker://ergebnis/github-action-template:1.2.3
```

## Changelog

Please have a look at [`CHANGELOG.md`](CHANGELOG.md).

## Contributing

Please have a look at [`CONTRIBUTING.md`](.github/CONTRIBUTING.md).

## Code of Conduct

Please have a look at [`CODE_OF_CONDUCT.md`](.github/CODE_OF_CONDUCT.md).

## License

This package is licensed using the MIT License.
