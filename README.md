Pre-commit hooks for OCaml code
==

A git pre-commit hook is a program that runs when you commit files
with git. This is a
[feature of git](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks),
which simply runs the script `.git/hooks/pre-commit` if there is one. We
manage this script with the help of a [third-party tool called `pre-commit`](https://pre-commit.com/).
It makes it easy to combine multiple checks and fixes for various
programming languages.

This repo provides hooks that are useful with OCaml code.

Hooks available
--

### `ocp-indent`

Sample `.pre-commit-config.yaml` file:

```
repos:
  - repo: https://github.com/returntocorp/pre-commit-ocaml
    rev: v1.0.0
    hooks:
      - id: ocp-indent
```

It will re-indent all the files ending in `.ml` or `.mli` using
[`ocp-indent`](https://www.typerex.org/ocp-indent.html).
`ocp-indent` must be installed by the user. It can be
installed with opam as follows:

```
opam install ocp-indent
```

Configuring `ocp-indent` can be done by placing a `.ocp-indent` file
at the root of the repository. A sample, conservative config that we like
is provided [here](example/.ocp-indent) for convenience.
