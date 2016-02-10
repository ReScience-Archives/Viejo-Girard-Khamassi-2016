### Required tools for producing the pdf

You'll need [pandoc](http://pandoc.org) (a universal document converter) and a
full [TeX distribution](https://www.tug.org/texlive/).

For pandoc, you'll also need the
[pandoc-crossref](https://github.com/lierdakil/pandoc-crossref) filter that you can
easily install with:

```
$ cabal update
$ cabal install pandoc-crossref
```

### How to build the PDF ?

In a console, type:

```
pandoc --standalone --filter ~/.cabal/bin/pandoc-crossref --template=rescience-template.tex --latex-engine=xelatex --biblatex --bibliography=viejo_girard_khamassi.bib -M "crossrefYaml=crossref.yaml" --output viejo_girard_khamassi.tex viejo_girard_khamassi.md
xelatex your_article_name
biber your_article_name
xelatex your_article_name
xelatex your_article_name
```

