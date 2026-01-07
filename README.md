---
abstract: A small demo embedding external content via xref. The content should be present in web and pdf exports, however it appears only in web.
exports:
  - format: pdf
    template: lapreprint
    output: exports/latex.pdf
    id: latex-export

  - format: typst
    template: lapreprint-typst
    output: exports/typst.pdf
    id: typst-export

downloads:
  - id: latex-export
    title: A latex-PDF of this document
  - id: typst-export
    title: A typst-PDF of this document
---

# BUG REPORT: embedding external content via xrefs

## Directly with the inline `![](xref:)` syntax
![](xref:mystguide#img:altair-horsepower)

## Passing the reference to the figure directive
```{figure} xref:mystguide#img:mpl
A matplotlib image of the cars data from the myst guide
```

## Same for Internal Reference

```{figure} #plt:sine
This is a sine wave, from a different document in the same project
```


## Separate Issue: Experimentation with wrapping embed in figure
leads to typst error

:::: {figure}
:::{embed} #plt:sine
:remove-output: false
:remove-input: false
:::

This is a figure caption for embedded content.
::::

:::{code-cell} python
:caption: A code-cell generating a sine plot

import numpy as np
import matplotlib.pyplot as plt
x = np.linspace(0, 8 * np.pi, 100)
y = np.sin(x)
_ = plt.plot(x, y)
:::