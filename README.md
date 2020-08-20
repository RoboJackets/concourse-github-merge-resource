# concourse-github-merge-resource
[![GitHub license](https://img.shields.io/github/license/RoboJackets/concourse-github-merge-resource)](https://github.com/RoboJackets/concourse-github-merge-resource/blob/main/LICENSE) [![CI](https://concourse.robojackets.org/api/v1/teams/information-technology/pipelines/github-merge/jobs/build-main/badge)](https://concourse.robojackets.org/teams/information-technology/pipelines/github-merge)

Concourse resource to automatically merge a pull request if it was opened by a bot

## Source configuration

- `pull_request` (required) - the resource where pull requests are provided
- `token` (required) - GitHub App token to use to authenticate
- `debug` (optional) - whether to enable debug logging; must be set to boolean true if present

GitHub endpoint information and the commit SHA will be derived from the environment.

## Behavior
Do not `get` this resource manually, it will not work.

### `check`
Returns an empty list.

### `in`
Does nothing.

### `out`
Merges the pull request if the author is a bot and it is in a mergeable state, otherwise does nothing.

You may want to [manually configure inputs](https://concourse-ci.org/jobs.html#schema.step.put-step.inputs) for better performance if you have large resources in your pipeline.
