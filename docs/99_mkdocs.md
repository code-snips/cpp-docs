# MkDocs

run with 
```sh
. venv\scripts\activate
mkdocs serve
```

For full documentation visit [mkdocs.org](https://www.mkdocs.org).

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.

## MkDocs Config

```
python --version
pip --version

C:\workspaces\cpp-docs\cpp-docs> python -m venv venv
C:\workspaces\cpp-docs\cpp-docs> . venv\scripts\activate

pip install mkdocs-material

mkdocs new .
mkdocs serve
```

## prompts
```
write a professional tutorial for modern c++ with the following topic: primitive datatypes
use the .md format to generate mkdocs. wrap codeblocks with *** instead of ``` put the whole response in a single codeblock
```