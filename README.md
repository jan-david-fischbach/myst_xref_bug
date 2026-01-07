---
title: SideBySide output to typst
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

kernelspec:
  name: python3
  display_name: 'Python 3'
---


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