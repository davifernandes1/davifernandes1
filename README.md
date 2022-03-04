@@ -7,21 +7,12 @@ on:
      - master
      - theme-preview-script
      - "themes/index.js"
  issue_comment:
    types: [edited]

jobs:
  comment:
    if: contains(github.event.comment.html_url, '/pull/')
    runs-on: ubuntu-latest
    steps:
      - name: say hello
        if: contains(github.event.comment.body, 'Automated Theme Preview')
        run: |
          echo say hello
  build:
    runs-on: ubuntu-latest
    name: Install & Preview

    steps:
      - uses: actions/checkout@v1
      - uses: bahmutov/npm-install@v1
