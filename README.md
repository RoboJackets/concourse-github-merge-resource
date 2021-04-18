# concourse-github-merge-resource
[![GitHub license](https://img.shields.io/github/license/RoboJackets/concourse-github-merge-resource)](https://github.com/RoboJackets/concourse-github-merge-resource/blob/main/LICENSE) [![CI](https://concourse.robojackets.org/api/v1/teams/information-technology/pipelines/github-merge/jobs/build-main/badge)](https://concourse.robojackets.org/teams/information-technology/pipelines/github-merge)

Concourse resource to automatically merge a pull request if it was opened by a bot

## Source configuration

- `pull_request_url` (required) - pull request that is being built
- `commit` (required) - commit that is being built
- `token` (required) - GitHub App token to use to authenticate
- `debug` (optional) - whether to enable debug logging; must be set to boolean true if present

## Behavior
Do not `get` this resource manually, it will not work.

### `check`
Returns an empty list.

### `in`
Does nothing.

### `out`
Merges the pull request if the author is a bot and it is in a mergeable state, otherwise does nothing.

`inputs` must be an empty list; this reduces overhead starting the container.
