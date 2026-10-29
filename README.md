# PanRocq

This is an example of a [Quarto book](https://quarto.org/docs/books) that uses PanRocq to highlight Rocq code. PanRocq also works with [Typst](https://typst.app/#start).

PanRocq's highlighting rules are based on the [Rocq-sublime](https://github.com/mattam82/rocq-sublime) syntax by [Matthieu Sozeau](https://sozeau.gitlabpages.inria.fr/www/) (MIT Licence, 2025).

## Basic setup

Add the files `PanRocq.theme` and `PanRocq.xml` to the root folder of your Quarto project. Then add the following `syntax-definitions` and `highlight-style` fields to the `_quarto.yml` file.

```yml
format:
  html:
    theme: cosmo
    syntax-definitions:
      - ./PanRocq.xml
    highlight-style: ./PanRocq.theme
  pdf:
    documentclass: scrreprt
    syntax-definitions:
      - ./PanRocq.xml
    highlight-style: ./PanRocq.theme
```

Any Quarto code block starting with a `rocq` fence will then be highlighted. See the [documentation](https://matematiflo.github.io/PanRocq/PanRocq.html#quarto) for dark mode usage.

## Example

Copy the following code block into `index.qmd` then run `quarto render`.

````markdown
```rocq
Definition negb (b : bool) : bool :=
  match b with
  | true  => false
  | false => true
  end.
```
````

## Using PanRocq with Typst

Add the files `Rocq.sublime-syntax` and `Rocq.tmTheme` to your Typst directory. Then add the following to your `.typ` file.

```typst
#set raw(syntaxes: "Rocq.sublime-syntax", lang: "rocq", theme: "Rocq.tmTheme")
```

Any Typst code block starting with a `rocq` fence will then be highlighted.

## Troubleshooting

Created using [Quarto 1.10.18](https://github.com/quarto-dev/quarto-cli). See the [documentation](https://matematiflo.github.io/PanRocq/Troubleshooting.html) for more.
