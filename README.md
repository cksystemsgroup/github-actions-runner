<p align="center">
  <img src="docs/res/github-graph.png">
</p>

# Hardened GitHub Actions Runner

This is a fork of the [upstream GitHub Actions runner][upstream] with
minor patches applied to allow deployment as a self-hosted runner for
public repositories. Please note that this is by no means a supported
version and just holds modifications suitable for our environment.

The following patches have been applied to this version:

* Checking of a specific `RUNNER_TOKEN` secret on the job. All jobs not
  providing a matching token will be canceled and hence prevented from
  running on the self-hosted runner. This allows all access control
  mechanisms already available for secrets to be used for managing
  runner access as well.
* Disabling of self-update by the runner. This prevents applied patches
  from being reverted by an upstream release.

Inspiration for these changes was taken from the following places:

* A very [similar fork][rustfork] used by the Rust Infrastructure Team.
* An [enhancement issue][enhissue] filed for the upstream runner.

Use at your own peril, here be dragons!

[upstream]: https://github.com/actions/runner
[rustfork]: https://github.com/rust-lang/gha-runner
[enhissue]: https://github.com/actions/runner/issues/631

---

# GitHub Actions Runner

[![Actions Status](https://github.com/actions/runner/workflows/Runner%20CI/badge.svg)](https://github.com/actions/runner/actions)
[![Runner E2E Test](https://github.com/actions/runner/workflows/Runner%20E2E%20Test/badge.svg)](https://github.com/actions/runner/actions)

The runner is the application that runs a job from a GitHub Actions workflow. It is used by GitHub Actions in the [hosted virtual environments](https://github.com/actions/virtual-environments), or you can [self-host the runner](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/about-self-hosted-runners) in your own environment.

## Get Started

For more information about installing and using self-hosted runners, see [Adding self-hosted runners](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/adding-self-hosted-runners) and [Using self-hosted runners in a workflow](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/using-self-hosted-runners-in-a-workflow)

Runner releases:

![win](docs/res/win_sm.png) [Pre-reqs](docs/start/envwin.md) | [Download](https://github.com/actions/runner/releases)  

![macOS](docs/res/apple_sm.png)  [Pre-reqs](docs/start/envosx.md) | [Download](https://github.com/actions/runner/releases)  

![linux](docs/res/linux_sm.png)  [Pre-reqs](docs/start/envlinux.md) | [Download](https://github.com/actions/runner/releases)

## Contribute

We accept contributions in the form of issues and pull requests.  [Read more here](docs/contribute.md) before contributing.
