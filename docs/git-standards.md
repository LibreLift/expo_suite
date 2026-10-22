# Git standards

How a change gets into this project. If you're contributing, this is how
we work; if you think a rule is wrong, open an issue and say why.

## Branch names

**The rule**: `type/issue#-two-words`. 

**Example**: `feat/31-integrated-timer`.

**The reason**: This allows branches to be easily categorized, and connects them directly to open issues. At any given moment we can know what work is being done on any issue by seeing the open branches for that issue.

## Commit messages

**The rule**: Follow [cbeam's 7 rules](https://cbea.ms/git-commit/) for useful commit messages, and prefix all commits with [conventional commit](https://www.conventionalcommits.org/en/v1.0.0/#summary) types.

**Example**:

```
fix: correct expected json payload for getTemplates endpoint

The getTemplates endpoint was expecting a single JSON object 
and was trying to serialize it into a WorkoutTemplate object.

The endpoint from the backend actually returns a list of 
JSON objects, so the frontend client was changed to 
expect that instead.
```

**The reason**: Similar to the branch names prefixes, conventional commit prefixes allow commits to be easily categorized. The type of work being done in a PR can be easily viewed from commit messages. Also, this format supports one-line summaries such as in GitHub, but provide more info when necessary. 

## Pull requests

**The rule**: Changes that resolve one issue, or 1,000 lines, whichever comes first. If an issue's resolution requires more than 1,000 lines of code, it should be decomposed.

**The reason**: PRs should be easily human reviewable, so they should be kept small and manageable in size.

## Review

**The rule**: At one approval from a contributor who did not author the PR

**The reason**: Having a fresh set of eyes can help expose untested assumptions. Also, having to explain a PR to someone independent of its development proves understanding.

## Merging

**The rule**: Only maintainers have permission to merge. The merging method that will be used is squash and merge.

**The reason**: Protecting the `main` branch by limiting merge permissions will keep the production code safe. Squash and merge will keep the history clean and linear, and allow entire features to be rolled back with one command if necessary.

## Definition of done

**The rule**: A PR is merged to `main` after adequate review and passing CI, and is verified in production. Then, and documentation change issues are filed, implemented, and completed.

**The reason**: A task is not truly "done" until we can verify that it works in production. Documentation updates is part of being "done" because that is part of the development process, not a separate, administrative one.