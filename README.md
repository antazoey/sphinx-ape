# Quick Start

`sphinx-ape` is a documenation plugin for the Sphinx framework.
The purpose of this plugin to share code for generating documentation across all ApeWorX repositories.

## Dependencies

- [python3](https://www.python.org/downloads) version 3.9 up to 3.12.

## Install

Install using `pip` or `uv` by either cloning this repo or accessing from pypi, e.g.:

```sh
pip install sphinx-ape
```

Try `sphinx-ape --help` to check if it's installed.

## Quick Usage

To use this sphinx plugin, first generate the docs structure (ran from your project directory):

```sh
sphinx-ape init .
```

It will have generated a `docs/` folder with some necessary config file in it, along with a quick-start that links to your `README.md`.

Now, you can begin writing your Sphinx documentation.
There are three directories you can place documentation sources in:

1. `userguides/` - a directory containing how-to guides for how to use your package.
2. `commands/` - `.rst` files for the `sphinx-click` plugin for CLI-based references.
3. `methoddocs/` - Autodoc `.rst` files controlling your generated method documentation.

Once you have developed your documentation, ensure you have `sphinx-ape` installed.
For example, clone this repo and install it using `pip install <path/to/sphinx-ape>` or install from `pypi` by doing `pip intall sphinx-ape`.

After `sphinx-ape` is installed, build your projects' documentation by doing:

```sh
sphinx-ape build <path/to/project>
```

Most commonly, you will already be in your project's directory, so you will do:

```sh
sphinx-ape build .
```

Then, to view the documentation, run the `serve` command:

```sh
sphinx-ape serve <path/to/project>
# When in directory already
sphinx-ape serve .
```

To automatically open a browser at the same time as serving, use the `--open` flag:

```sh
sphinx-ape serve . --open
```

## GitHub Action

This GitHub action is meant for building the documentation in both core Ape as well any Ape plugin.
The aciton may also work for regular Python packages with a documentation-strategy similar to Ape.

There are three GitHub events that trigger this action:

1. Push to 'main': we build into 'latest/'.
   The GitHub action will commit these changes to the 'gh-pages' branch.

2. Release: we copy 'latest/' into the release dir, as well as to 'stable/'.
   The GitHub action will commit these changes to the 'gh-pages' branch.

3. Pull requests or local development: We ensure a successful build.

## GitHub Pages

To set up this action with GitHub pages for the release-workflow to work, first create a branch named `gh-pages` and push it to GitHub.
Then, delete everything besides a simple `README.md`, the `.gitignore` file, and the `LICENSE` file.
Once that is all pushed, verify on the Pages tab that a site was made for you.
Now, on merges to main and releases, this site should be updated (if you are using the action).

## Development

Please see the [contributing guide](CONTRIBUTING.md) to learn more how to contribute to this project.
Comments, questions, criticisms and pull requests are welcomed.