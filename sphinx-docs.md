# Tips for creating a documentation page with sphinx

Sphinx is a neat little Python library that can convert many different
types of text files into html pages, pdf files, etc. For this you will
need to have the following installed in the python environment of
choice:

- sphinx
- nbsphinx

To create the docs you can then run

```bash
mkdir docs
cd docs
sphinx-quickstart
```

And work through the menu prompts it gives. We recommend that you *DO*
separate the source and build directories (first prompt). It is not
required to run it in a different directory, but it can be helpful for
organization purposes. Especially when this is attached to a code base
as it will create a `Makefile` for compiling everything.

After the program has run you should see two directories, `source` and
`build`, a `Makefile` and a `make.bat` file. In the `source` directory
there are a set of files

- `index.rst`: Main index file that can serve as the homepage for the
  website or documentation.
- `conf.py`: Configuration script with directives on how to build the
  documentation. Can handle what extensions are included, `extensions`
  variable, and the HTML theme to use, `html_theme` variable.

Have to remember to set the "Workflow permissions" to "Read and write
permissions". This can be found in Settings -> Actions -> General ->
Workflow permissions. What this will allow you to do is to push to a
branch when building the documentation and pushing the HTML pages to the
gh-pages branch in your repository.



