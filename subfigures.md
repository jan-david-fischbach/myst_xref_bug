---
title: Demo of subfigures bug in typst
exports:
  - format: pdf
    template: lapreprint
    output: exports/subfigs_latex.pdf
    id: subfigs-latex-export

  - format: typst
    template: lapreprint-typst
    output: exports/subfigs_typst.pdf
    id: subfigs-typst-export

downloads:
  - id: subfigs-latex-export
    title: A latex-PDF of this document
  - id: subfigs-typst-export
    title: A typst-PDF of this document

kernelspec:
  name: python3
  display_name: 'Python 3'
---

## Simple subfigure example that works in latex, and in the web-version but not in typst:

:::{figure}
:label: my-figure
:align: left

(my-figure-fruit)=
![Here is some fruit 🍏](assets/apples-wide.png)

![My vacation pics! 🏝](assets/ocean-wide.png)

Some pictures of fruit and the ocean!
:::

## Separate Issue: Experimentation with wrapping embed in figure
Leads to typst error

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