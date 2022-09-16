# Actions environment name sanitation

This repository contains a Github action which purpose is to sanitize a git branch name by removing all non alphanumeric characters and by adding a `test-` prefix.

**Example**

Before                   | After
------------------------ | -------------
`feature/awesome`        | `test-featureawesome`
`hotfix-prod-is-on-fire` | `test-hotfixprodisonfire`
`feat`                   | `test-feat`

## Usage

Use this action in your pipeline:

```yaml
- name: Set environment name from branch name
  uses: planday-corp/actions-environment-name-sanitation@v1
  id: set_environment_name

- run: echo "${{steps.set_environment_name.outputs.environment_name}}"
  shell: bash
```