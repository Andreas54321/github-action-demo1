# Actions

Split up into some steps:

- test
- build
- deploy (deps)

## Retrieve Artifacts

```yml
- name: Get artifacts
  uses: actions/download-artifact@v3
  id: myId # optional Step Id to access path
  with:
    name: dist-files # artifact name
    path: outputFolder # optional
```

Output:
${{ steps.[stepId].outputs.download-path }}
