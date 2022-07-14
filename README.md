# tracee-action-example

An example repo to show how tracee can be configured as a GitHub Action.

tl;dr – Simplest example
```
name: Tracee Pipeline Scan
on: [pull_request]

jobs:
  Tracee-Scan:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2

    - name: Start Tracee profiling in background
      uses: aquasecurity/tracee-action@v0.1.0-start

    - name: Your CI Pipeline Step
      run: pip install dateutils

    - name: Stop and Check Tracee results and create a PR
      uses: aquasecurity/tracee-action@v0.1.0-stop
      with:
        fail-on-diff: "true"
        create-pr: "true"
```
