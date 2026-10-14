# fork-active-repo-sync

Keeps [olivwalsh/fork-active-repo-test](https://github.com/olivwalsh/fork-active-repo-test), a fork of
[home-assistant/core](https://github.com/home-assistant/core), in sync with its upstream every 5 minutes.

The fork is a test repository: its pushes feed a compaction experiment, so the sync runs in this separate
repository to keep the fork free of any commit that upstream does not have (which would break fast-forward syncs).

## Setup

Add a repository secret named `SYNC_PAT`: a personal access token with write access to the fork's
contents and workflows.

```bash
gh secret set SYNC_PAT -R olivwalsh/fork-active-repo-sync
```

Then run the workflow once by hand from the Actions tab (`workflow_dispatch`) to check it.
