# Custom GitHub Action

This is a custom GitHub Action that can be used in a workflow (such as a CI/CD pipeline) to perform a specific task.

## How to create a custom GitHub Action

To create a custom GitHub Action you can use a Docker container, a JavaScript or a composite action.

In this example we will use a Docker container.

### Create a Dockerfile

You need a Dockerfile to create a Docker image that will be used to run the action. [Here](Dockerfile) is an example of a Dockerfile.

### Create an entrypoint.sh file

You need an entrypoint.sh file to define the steps that will be executed when the action is run. [Here](entrypoint.sh) is an example of an entrypoint.sh file.

### Create an action.yml file

You need an action.yml file to define the inputs and outputs of the action. [Here](action.yml) is an example of an action.yml file.

### Example of a workflow that uses the custom GitHub Action

```yaml
name: Custom GitHub Action

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Run custom GitHub Action
        uses: returngis/custom-github-action@main
        with:
          who-to-greet: 'Gisela Torres'
```

You can see it in action in this repository's [workflow](.github/workflows/main.yml).