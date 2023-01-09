# Actions

See all actions there: [github.com/marketplace](https://github.com/marketplace?type=actions)

## Checkout Code

```yml
steps:
  - name: Get code # Step name
    uses: actions/checkout@v3 # Action
```

## Shell command

```yml
- name: Install dependencies
  run: npm ci
  working-directory: ./temp # optional
  shell: bash # optional, see docu
```

## Save Artifacts

```yml
- name: Upload artifacts
  uses: actions/upload-artifact@v3
  with:
    name: dist-files # artifact name
    path: | # list of folders
      dist
      other
    retention-days: 90 # optional, default 90
```

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
