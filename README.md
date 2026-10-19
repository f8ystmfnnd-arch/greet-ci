# greet-ci

Week07 greeting program and GitHub Actions CI practice.

## Setup and run

Install Git and uv. Run these commands from the repository root:

```sh
uv sync --locked
uv run --locked python greet.py Hee
uv run --locked python greet.py
```

The commands print `Hello, Hee!` and `Hello, world!`, respectively.

## Check and build

```sh
uv run --locked pytest -q greet.py
uv run --locked black --check greet.py
uv run --locked flake8 greet.py
uv run --locked mypy greet.py
uv build
```

CI uses uv 0.8.14. Pull requests targeting main and pushes to main run
tests on Ubuntu and Windows with Python 3.11 and 3.12, followed by
quality checks and a package build. The build uploads the wheel and
source distribution as the `greet-dist` artifact.
