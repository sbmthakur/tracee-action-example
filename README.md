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
      uses: simar7/tracee-action@v0.2.0-start

    - name: Your CI Pipeline Step
      run: for i in {1..20}; do sleep 2 && strace ls; done

    - name: Stop and Check Tracee results and create a PR
      uses: simar7/tracee-action@v0.3.0-stop
```
