# Start

## Wokflow events/triggers

More types:

```yml
on:
  workflow_dispatch: # manual trigger
  pull_request: # on pull
    types: # >> Activity Types
      - opened # see docu
    branches: # >> Event Filter
      - main
      - "dev-*"
      - "feat/**"
  push: # on push, see docu
    branches:
      - main
      - "dev-*"
      - "feat/**"
    paths-ignore:
      - ".github/workflows/*"
```
