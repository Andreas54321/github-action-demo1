# Actions

## Cache Folder

```yml
- name: Cache dependencies
  uses: actions/cache@v3
  with:
    path: ~/.node_modules
    key: deps-node-modules-$${{ hashFiles('**/package-lock.json') }}
```

check with:

```yml
if: steps.[id].outputs.cache-hit != 'true'
```

Or just cach `~/.npm` Folder instead!

Establish data, initialize cache after job execution

## Conditions

Special Condition functions:
Trigger follow up steps to be executed:

```yml
 - name: Upload test report
   if: failure() && steps.[id].outcome == 'failure'

failure()   # on error
success()   # on all success
always()    # true
cancelled() # on canceled
```

Ignore failing step and continue:

```yml
continue-on-error: true # ignore failing
```
