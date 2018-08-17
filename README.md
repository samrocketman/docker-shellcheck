# Dockerized ShellCheck

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/MyDockerfiles/ShellCheck)
[![Docker Hub pulls](https://img.shields.io/docker/pulls/peterdavehello/shellcheck.svg)](https://hub.docker.com/r/peterdavehello/shellcheck/)
[![Docker image layers](https://images.microbadger.com/badges/image/peterdavehello/shellcheck.svg)](https://microbadger.com/images/peterdavehello/shellcheck/)
[![Docker image version](https://images.microbadger.com/badges/version/peterdavehello/shellcheck.svg)](https://hub.docker.com/r/peterdavehello/shellcheck/tags/)

[![Docker Hub badge](http://dockeri.co/image/peterdavehello/shellcheck)](https://hub.docker.com/r/peterdavehello/shellcheck/)

## About ShellCheck

A static analysis tool for shell scripts, homepage and repository below:

- https://www.shellcheck.net
- https://github.com/koalaman/shellcheck

Please note that this Docker image repository is not part of the ShellCheck project.

## Usage

### Command line

```sh
$ docker run --rm -it -v `pwd`:/scripts peterdavehello/shellcheck shellcheck /scripts/script.sh
```

### In GitLab or other Docker native CI

```yaml
shellcheck:
  stage: test
  image: peterdavehello/shellcheck:0.5.0
  before_script:
    - shellcheck --version
  script:
    - find . -name "*.sh" | xargs -n 1 shellcheck --color=always
  tags:
    - docker
```
