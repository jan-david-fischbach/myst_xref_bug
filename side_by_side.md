---
title: Side-by-side subfigures with embed
abstract: Subfigures demo
exports:

  - format: typst
    template: ./typst-template
    output: exports/subfigs_typst.pdf
    id: subfigs-typst-export

kernelspec:
  name: python3
  display_name: 'Python 3'
---

```{raw:typst}
#set page(margin: auto)
```

## Experimentation with wrapping embed in figure

:::::: {figure}

::::: {figure}
::::{card}
:::{embed} #plt:sine
:remove-output: true
:remove-input: false
:::
::::
:::::

:::: {figure}
:::{embed} #plt:sine
:remove-output: false
:remove-input: true
:::
::::

This is a figure caption for embedded content.
::::::

<!-- :::{code-cell} python
:caption: A code-cell generating a sine plot

import numpy as np
import matplotlib.pyplot as plt
x = np.linspace(0, 8 * np.pi, 100)
y = np.sin(x)
_ = plt.plot(x, y)
::: -->

::::{side-by-side} #plt:sine
Caption text goes here
::::

## just card with embed

::::{card} Code
:::{embed} #plt:sine
:remove-output: true
:remove-input: false
:::
::::

