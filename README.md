# pandoc-plot - A pandoc filter to generate figures directly from documents

`pandoc-plot` turns code blocks present in your documents into embedded figures, using your plotting toolkit of choice.

* [Usage](#usage)
* [Supported toolkits](#supported-toolkits)

## Usage

The filter recognizes code blocks with classes that match plotting toolkits. For example, using the `matplotlib` toolkit:

~~~markdown
# My document

This is a paragraph.

```{.matplotlib}
import matplotlib.pyplot as plt

plt.figure()
plt.plot([0,1,2,3,4], [1,2,3,4,5])
plt.title('This is an example figure')
```
~~~

Putting the above in `input.md`, we can then generate the plot and embed it in an HTML page:

```bash
pandoc --filter pandoc-plot input.md --output output.html
```

## Supported toolkits

`pandoc-plot` currently supports the following plotting toolkits (installed separately):

* `matplotlib`: plots using the [matplotlib](https://matplotlib.org/) Python library;
* `plotly` : plots using the [plotly](https://plot.ly/python/) Python library;
* `matlabplot`: plots using the [MATLAB](https://www.mathworks.com/) plotting environment;

### In progress

Support for the following plotting toolkits is coming:

* [gnuplot](http://www.gnuplot.info/)
* [Plotly R](https://plot.ly/r/)
* [ggplot2](https://ggplot2.tidyverse.org/)
* [Mathematica](https://www.wolfram.com/mathematica)

Wish your plotting toolkit of choice was available? Please [raise an issue](https://github.com/LaurentRDC/pandoc-plot/issues)!
