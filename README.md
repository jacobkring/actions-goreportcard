# Actions Go Report Card

A composite github action template for running goreportcard-cli and grabbing the output for use elsewhere

## Motivation

I contribute to a number of private Golang repos that make it inconvenient to use 3rd party tools for things like goreportcard.com.

## Usage

#### Workflow

In your workflow file you should include the inputs you want.
```
on: [push]

jobs:
  action_goreportcard:
    runs-on: ubuntu-latest
    name: A job to run go report card
    steps:
      - name: Go Report Card
        id: goreportcard
        uses: jacobkring/actions-goreportcard@v0.0.1
        with:
          threshold: "-t 85"
          verbose: "-v"
      - name: results
        run: |
          echo ${{ steps.goreportcard.outputs.summary}}
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[Apache v2.0](https://tldrlegal.com/license/apache-license-2.0-(apache-2.0))
