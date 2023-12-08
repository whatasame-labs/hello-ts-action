# hello-ts-action

This GitHub action is simple implementation based TypeScript
using [typescript-action](https://github.com/actions/typescript-action) template.

## Usage

To run this action, you can use the below instructions.

1. Create a `.github/workflows/hello-ts-action.yml` file in your repository.
2. Add the following code to the `hello-ts-action.yml` file.
3. Commit and push the changes to the repository.

```yaml
name: Hello TypeScript Action

on: [ push ]

jobs:
  hello-ts-action:
    name: Run hello-ts-action application
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        id: checkout
        uses: actions/checkout@v4

      - name: Run hello-ts-action
        id: test-action
        uses: whatasame-labs/hello-ts-action@v1 # Commit with the `v1` tag
        with:
          milliseconds: 1000
          who-to-greet: 'whatasame' # Insert target name

      - name: Print Output
        id: output
        run: echo "${{ steps.test-action.outputs.time }}"
```

If you want to run this action on your existing workflow, you can add only a `hello-ts-action` job to your workflow.
