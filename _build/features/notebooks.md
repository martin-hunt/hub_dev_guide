---
interact_link: content/features/notebooks.ipynb
kernel_name: python3
has_widgets: false
title: 'Features and customization'
prev_page:
  url: /https://github.com/jupyter/jupyter-book
  title: 'GitHub repository'
next_page:
  url: /features/notebooks
  title: 'Jupyter notebooks'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

# Content with notebooks

You can also create content with Jupyter Notebooks. The content for the current page is contained
in a Jupyter Notebook in the `notebooks/` folder of the repository. This means that we can include
code blocks and their outputs, and export them to Jekyll markdown.

**You can find the original notebook for this page [at this address](https://github.com/jupyter/textbooks-with-jupyter/blob/master/notebooks/introduction/notebooks.ipynb)**

## Markdown + notebooks

As it is markdown, you can embed images, HTML, etc into your posts!

![](cool.jpg)

You an also $add_{math}$ and

$$
math^{blocks}
$$

or

$$
\begin{align*}
\mbox{mean} la_{tex} \\ \\
math blocks
\end{align*}
$$

But make sure you \\$Escape \\$your \\$dollar signs \\$you want to keep!

## Code blocks and image outputs

Textbooks with Jupyter will also embed your code blocks and output in your site.
For example, here's some sample Matplotlib code:



{:.input_area}
```python
from matplotlib import rcParams, cycler
import matplotlib.pyplot as plt
import numpy as np
plt.ion()
```




{:.input_area}
```python
# Fixing random state for reproducibility
np.random.seed(19680801)

N = 10
data = [np.logspace(0, 1, 100) + np.random.randn(100) + ii for ii in range(N)]
data = np.array(data).T
cmap = plt.cm.coolwarm
rcParams['axes.prop_cycle'] = cycler(color=cmap(np.linspace(0, 1, N)))


from matplotlib.lines import Line2D
custom_lines = [Line2D([0], [0], color=cmap(0.), lw=4),
                Line2D([0], [0], color=cmap(.5), lw=4),
                Line2D([0], [0], color=cmap(1.), lw=4)]

fig, ax = plt.subplots(figsize=(10, 5))
lines = ax.plot(data)
ax.legend(custom_lines, ['Cold', 'Medium', 'Hot']);
```



{:.output .output_png}
![png](../images/features/notebooks_2_0.png)



Note that the image above is captured and displayed by Jekyll.

## Removing content before publishing

You can also remove some content before publishing your book to the web. For example,
in [the original notebook](https://github.com/jupyter/jupyter-book/blob/master/notebooks/introduction/notebooks.ipynb) there
used to be a cell below...



{:.input_area}
```python
# HIDDEN
thisvariable = "none of this should show up in the textbook"

fig, ax = plt.subplots()
x = np.random.randn(100)
y = np.random.randn(100)
ax.scatter(x, y, s=np.abs(x*100), c=x, cmap=plt.cm.coolwarm)
ax.text(0, .5, thisvariable, fontsize=20, transform=ax.transAxes)
ax.set_axis_off()
```



{:.output .output_png}
![png](../images/features/notebooks_5_0.png)



You can also **remove only the code** so that images and other output still show up.

Below we'll *only* display an image. It was generated with Python code in a cell,
which you can [see in the original notebook](https://github.com/jupyter/jupyter-book/blob/master/notebooks/introduction/notebooks.ipynb)



{:.input_area}
```python
# NO CODE
thisvariable = "this plot *will* show up in the textbook."

fig, ax = plt.subplots()
x = np.random.randn(100)
y = np.random.randn(100)
ax.scatter(x, y, s=np.abs(x*100), c=x, cmap=plt.cm.coolwarm)
ax.text(0, .5, thisvariable, fontsize=20, transform=ax.transAxes)
ax.set_axis_off()
```



{:.output .output_png}
![png](../images/features/notebooks_7_0.png)



And here we'll *only* display a Pandas DataFrame. Again, this was generated with Python code
from [this original notebook](https://github.com/jupyter/textbooks-with-jupyter/blob/master/notebooks/introduction/notebooks.ipynb).



{:.input_area}
```python
# NO CODE
import pandas as pd
pd.DataFrame([['hi', 'there'], ['this', 'is'], ['a', 'DataFrame']], columns=['Word A', 'Word B'])
```





<div markdown="0" class="output output_html">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Word A</th>
      <th>Word B</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>hi</td>
      <td>there</td>
    </tr>
    <tr>
      <th>1</th>
      <td>this</td>
      <td>is</td>
    </tr>
    <tr>
      <th>2</th>
      <td>a</td>
      <td>DataFrame</td>
    </tr>
  </tbody>
</table>
</div>
</div>



You can configure the text that *Textbooks with Jupyter* uses for this by modifying your site's `_config.yml` file.

## Interactive outputs

We can even do the same for *interactive* material. Below we'll display a map using `ipyleaflet`. When the notebook
is converted to Markdown, the code for creating the interactive map is retained.

**Note that this will only work for some packages.** They need to be able to output standalone HTML/Javascript, and not
depend on an underlying Python kernel to work.



{:.input_area}
```python
import folium
```




{:.input_area}
```python
m = folium.Map(
    location=[45.372, -121.6972],
    zoom_start=12,
    tiles='Stamen Terrain'
)

folium.Marker(
    location=[45.3288, -121.6625],
    popup='Mt. Hood Meadows',
    icon=folium.Icon(icon='cloud')
).add_to(m)

folium.Marker(
    location=[45.3311, -121.7113],
    popup='Timberline Lodge',
    icon=folium.Icon(color='green')
).add_to(m)

folium.Marker(
    location=[45.3300, -121.6823],
    popup='Some Other Location',
    icon=folium.Icon(color='red', icon='info-sign')
).add_to(m)


m

```





<div markdown="0" class="output output_html">
<div style="width:100%;"><div style="position:relative;width:100%;height:0;padding-bottom:60%;"><iframe src="data:text/html;charset=utf-8;base64,PCFET0NUWVBFIGh0bWw+CjxoZWFkPiAgICAKICAgIDxtZXRhIGh0dHAtZXF1aXY9ImNvbnRlbnQtdHlwZSIgY29udGVudD0idGV4dC9odG1sOyBjaGFyc2V0PVVURi04IiAvPgogICAgPHNjcmlwdD5MX1BSRUZFUl9DQU5WQVM9ZmFsc2U7IExfTk9fVE9VQ0g9ZmFsc2U7IExfRElTQUJMRV8zRD1mYWxzZTs8L3NjcmlwdD4KICAgIDxzY3JpcHQgc3JjPSJodHRwczovL2Nkbi5qc2RlbGl2ci5uZXQvbnBtL2xlYWZsZXRAMS40LjAvZGlzdC9sZWFmbGV0LmpzIj48L3NjcmlwdD4KICAgIDxzY3JpcHQgc3JjPSJodHRwczovL2NvZGUuanF1ZXJ5LmNvbS9qcXVlcnktMS4xMi40Lm1pbi5qcyI+PC9zY3JpcHQ+CiAgICA8c2NyaXB0IHNyYz0iaHR0cHM6Ly9tYXhjZG4uYm9vdHN0cmFwY2RuLmNvbS9ib290c3RyYXAvMy4yLjAvanMvYm9vdHN0cmFwLm1pbi5qcyI+PC9zY3JpcHQ+CiAgICA8c2NyaXB0IHNyYz0iaHR0cHM6Ly9jZG5qcy5jbG91ZGZsYXJlLmNvbS9hamF4L2xpYnMvTGVhZmxldC5hd2Vzb21lLW1hcmtlcnMvMi4wLjIvbGVhZmxldC5hd2Vzb21lLW1hcmtlcnMuanMiPjwvc2NyaXB0PgogICAgPGxpbmsgcmVsPSJzdHlsZXNoZWV0IiBocmVmPSJodHRwczovL2Nkbi5qc2RlbGl2ci5uZXQvbnBtL2xlYWZsZXRAMS40LjAvZGlzdC9sZWFmbGV0LmNzcyIvPgogICAgPGxpbmsgcmVsPSJzdHlsZXNoZWV0IiBocmVmPSJodHRwczovL21heGNkbi5ib290c3RyYXBjZG4uY29tL2Jvb3RzdHJhcC8zLjIuMC9jc3MvYm9vdHN0cmFwLm1pbi5jc3MiLz4KICAgIDxsaW5rIHJlbD0ic3R5bGVzaGVldCIgaHJlZj0iaHR0cHM6Ly9tYXhjZG4uYm9vdHN0cmFwY2RuLmNvbS9ib290c3RyYXAvMy4yLjAvY3NzL2Jvb3RzdHJhcC10aGVtZS5taW4uY3NzIi8+CiAgICA8bGluayByZWw9InN0eWxlc2hlZXQiIGhyZWY9Imh0dHBzOi8vbWF4Y2RuLmJvb3RzdHJhcGNkbi5jb20vZm9udC1hd2Vzb21lLzQuNi4zL2Nzcy9mb250LWF3ZXNvbWUubWluLmNzcyIvPgogICAgPGxpbmsgcmVsPSJzdHlsZXNoZWV0IiBocmVmPSJodHRwczovL2NkbmpzLmNsb3VkZmxhcmUuY29tL2FqYXgvbGlicy9MZWFmbGV0LmF3ZXNvbWUtbWFya2Vycy8yLjAuMi9sZWFmbGV0LmF3ZXNvbWUtbWFya2Vycy5jc3MiLz4KICAgIDxsaW5rIHJlbD0ic3R5bGVzaGVldCIgaHJlZj0iaHR0cHM6Ly9yYXdjZG4uZ2l0aGFjay5jb20vcHl0aG9uLXZpc3VhbGl6YXRpb24vZm9saXVtL21hc3Rlci9mb2xpdW0vdGVtcGxhdGVzL2xlYWZsZXQuYXdlc29tZS5yb3RhdGUuY3NzIi8+CiAgICA8c3R5bGU+aHRtbCwgYm9keSB7d2lkdGg6IDEwMCU7aGVpZ2h0OiAxMDAlO21hcmdpbjogMDtwYWRkaW5nOiAwO308L3N0eWxlPgogICAgPHN0eWxlPiNtYXAge3Bvc2l0aW9uOmFic29sdXRlO3RvcDowO2JvdHRvbTowO3JpZ2h0OjA7bGVmdDowO308L3N0eWxlPgogICAgCiAgICA8bWV0YSBuYW1lPSJ2aWV3cG9ydCIgY29udGVudD0id2lkdGg9ZGV2aWNlLXdpZHRoLAogICAgICAgIGluaXRpYWwtc2NhbGU9MS4wLCBtYXhpbXVtLXNjYWxlPTEuMCwgdXNlci1zY2FsYWJsZT1ubyIgLz4KICAgIDxzdHlsZT4jbWFwXzIzN2Q4ZGY4ODc5YjRmZWJiNjg1ODIxN2JiMGViOWFlIHsKICAgICAgICBwb3NpdGlvbjogcmVsYXRpdmU7CiAgICAgICAgd2lkdGg6IDEwMC4wJTsKICAgICAgICBoZWlnaHQ6IDEwMC4wJTsKICAgICAgICBsZWZ0OiAwLjAlOwogICAgICAgIHRvcDogMC4wJTsKICAgICAgICB9CiAgICA8L3N0eWxlPgo8L2hlYWQ+Cjxib2R5PiAgICAKICAgIAogICAgPGRpdiBjbGFzcz0iZm9saXVtLW1hcCIgaWQ9Im1hcF8yMzdkOGRmODg3OWI0ZmViYjY4NTgyMTdiYjBlYjlhZSIgPjwvZGl2Pgo8L2JvZHk+CjxzY3JpcHQ+ICAgIAogICAgCiAgICAKICAgICAgICB2YXIgYm91bmRzID0gbnVsbDsKICAgIAoKICAgIHZhciBtYXBfMjM3ZDhkZjg4NzliNGZlYmI2ODU4MjE3YmIwZWI5YWUgPSBMLm1hcCgKICAgICAgICAnbWFwXzIzN2Q4ZGY4ODc5YjRmZWJiNjg1ODIxN2JiMGViOWFlJywgewogICAgICAgIGNlbnRlcjogWzQ1LjM3MiwgLTEyMS42OTcyXSwKICAgICAgICB6b29tOiAxMiwKICAgICAgICBtYXhCb3VuZHM6IGJvdW5kcywKICAgICAgICBsYXllcnM6IFtdLAogICAgICAgIHdvcmxkQ29weUp1bXA6IGZhbHNlLAogICAgICAgIGNyczogTC5DUlMuRVBTRzM4NTcsCiAgICAgICAgem9vbUNvbnRyb2w6IHRydWUsCiAgICAgICAgfSk7CgoKICAgIAogICAgdmFyIHRpbGVfbGF5ZXJfY2Y3ZGNmMWU4MzFhNDE5YjgzMWU4YzBmYjU5ZGI4MmYgPSBMLnRpbGVMYXllcigKICAgICAgICAnaHR0cHM6Ly9zdGFtZW4tdGlsZXMte3N9LmEuc3NsLmZhc3RseS5uZXQvdGVycmFpbi97en0ve3h9L3t5fS5qcGcnLAogICAgICAgIHsKICAgICAgICAiYXR0cmlidXRpb24iOiBudWxsLAogICAgICAgICJkZXRlY3RSZXRpbmEiOiBmYWxzZSwKICAgICAgICAibWF4TmF0aXZlWm9vbSI6IDE4LAogICAgICAgICJtYXhab29tIjogMTgsCiAgICAgICAgIm1pblpvb20iOiAwLAogICAgICAgICJub1dyYXAiOiBmYWxzZSwKICAgICAgICAib3BhY2l0eSI6IDEsCiAgICAgICAgInN1YmRvbWFpbnMiOiAiYWJjIiwKICAgICAgICAidG1zIjogZmFsc2UKfSkuYWRkVG8obWFwXzIzN2Q4ZGY4ODc5YjRmZWJiNjg1ODIxN2JiMGViOWFlKTsKICAgIAogICAgICAgIHZhciBtYXJrZXJfMGY1ZTcyNmYwZDBiNDM1YjliZjNkNzc2ZTY3MDM3YzYgPSBMLm1hcmtlcigKICAgICAgICAgICAgWzQ1LjMyODgsIC0xMjEuNjYyNV0sCiAgICAgICAgICAgIHsKICAgICAgICAgICAgICAgIGljb246IG5ldyBMLkljb24uRGVmYXVsdCgpLAogICAgICAgICAgICAgICAgfQogICAgICAgICAgICApLmFkZFRvKG1hcF8yMzdkOGRmODg3OWI0ZmViYjY4NTgyMTdiYjBlYjlhZSk7CiAgICAgICAgCiAgICAKCiAgICAgICAgICAgICAgICB2YXIgaWNvbl80MGE4YmM2YWRjZDA0YTBmYWM5ZjIyNDkzMDE1OThjZiA9IEwuQXdlc29tZU1hcmtlcnMuaWNvbih7CiAgICAgICAgICAgICAgICAgICAgaWNvbjogJ2Nsb3VkJywKICAgICAgICAgICAgICAgICAgICBpY29uQ29sb3I6ICd3aGl0ZScsCiAgICAgICAgICAgICAgICAgICAgbWFya2VyQ29sb3I6ICdibHVlJywKICAgICAgICAgICAgICAgICAgICBwcmVmaXg6ICdnbHlwaGljb24nLAogICAgICAgICAgICAgICAgICAgIGV4dHJhQ2xhc3NlczogJ2ZhLXJvdGF0ZS0wJwogICAgICAgICAgICAgICAgICAgIH0pOwogICAgICAgICAgICAgICAgbWFya2VyXzBmNWU3MjZmMGQwYjQzNWI5YmYzZDc3NmU2NzAzN2M2LnNldEljb24oaWNvbl80MGE4YmM2YWRjZDA0YTBmYWM5ZjIyNDkzMDE1OThjZik7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF9iNWMyZmUyMjFjNmE0ZDE5YTJiYWQzMDYxM2E3NmEyYSA9IEwucG9wdXAoe21heFdpZHRoOiAnMTAwJScKICAgICAgICAgICAgCiAgICAgICAgICAgIH0pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF8yODBjMzNlYWIzNWE0MmUzYjUxNjQ2ODAxMDIwZjM5NyA9ICQoYDxkaXYgaWQ9Imh0bWxfMjgwYzMzZWFiMzVhNDJlM2I1MTY0NjgwMTAyMGYzOTciIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPk10LiBIb29kIE1lYWRvd3M8L2Rpdj5gKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwX2I1YzJmZTIyMWM2YTRkMTlhMmJhZDMwNjEzYTc2YTJhLnNldENvbnRlbnQoaHRtbF8yODBjMzNlYWIzNWE0MmUzYjUxNjQ2ODAxMDIwZjM5Nyk7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgbWFya2VyXzBmNWU3MjZmMGQwYjQzNWI5YmYzZDc3NmU2NzAzN2M2LmJpbmRQb3B1cChwb3B1cF9iNWMyZmUyMjFjNmE0ZDE5YTJiYWQzMDYxM2E3NmEyYSkKICAgICAgICAgICAgOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICB2YXIgbWFya2VyX2E2ZmFhNTNjOGUwZDQwZGFiZGZmOTRjNmU0ZTRmNmQ4ID0gTC5tYXJrZXIoCiAgICAgICAgICAgIFs0NS4zMzExLCAtMTIxLjcxMTNdLAogICAgICAgICAgICB7CiAgICAgICAgICAgICAgICBpY29uOiBuZXcgTC5JY29uLkRlZmF1bHQoKSwKICAgICAgICAgICAgICAgIH0KICAgICAgICAgICAgKS5hZGRUbyhtYXBfMjM3ZDhkZjg4NzliNGZlYmI2ODU4MjE3YmIwZWI5YWUpOwogICAgICAgIAogICAgCgogICAgICAgICAgICAgICAgdmFyIGljb25fY2E1YjE1YmU0YmZlNDdhYTk4NDZlN2Q0MTg4MGM2YzAgPSBMLkF3ZXNvbWVNYXJrZXJzLmljb24oewogICAgICAgICAgICAgICAgICAgIGljb246ICdpbmZvLXNpZ24nLAogICAgICAgICAgICAgICAgICAgIGljb25Db2xvcjogJ3doaXRlJywKICAgICAgICAgICAgICAgICAgICBtYXJrZXJDb2xvcjogJ2dyZWVuJywKICAgICAgICAgICAgICAgICAgICBwcmVmaXg6ICdnbHlwaGljb24nLAogICAgICAgICAgICAgICAgICAgIGV4dHJhQ2xhc3NlczogJ2ZhLXJvdGF0ZS0wJwogICAgICAgICAgICAgICAgICAgIH0pOwogICAgICAgICAgICAgICAgbWFya2VyX2E2ZmFhNTNjOGUwZDQwZGFiZGZmOTRjNmU0ZTRmNmQ4LnNldEljb24oaWNvbl9jYTViMTViZTRiZmU0N2FhOTg0NmU3ZDQxODgwYzZjMCk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF8wMjg5YTQzMzBkMjg0NDcyYWIzYjhhYWI4YTExNDM5YyA9IEwucG9wdXAoe21heFdpZHRoOiAnMTAwJScKICAgICAgICAgICAgCiAgICAgICAgICAgIH0pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF9lY2Y1OWQ1MGRjYTU0YTA5YjFmYjljZGIzNGQyYzY1YSA9ICQoYDxkaXYgaWQ9Imh0bWxfZWNmNTlkNTBkY2E1NGEwOWIxZmI5Y2RiMzRkMmM2NWEiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPlRpbWJlcmxpbmUgTG9kZ2U8L2Rpdj5gKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwXzAyODlhNDMzMGQyODQ0NzJhYjNiOGFhYjhhMTE0MzljLnNldENvbnRlbnQoaHRtbF9lY2Y1OWQ1MGRjYTU0YTA5YjFmYjljZGIzNGQyYzY1YSk7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgbWFya2VyX2E2ZmFhNTNjOGUwZDQwZGFiZGZmOTRjNmU0ZTRmNmQ4LmJpbmRQb3B1cChwb3B1cF8wMjg5YTQzMzBkMjg0NDcyYWIzYjhhYWI4YTExNDM5YykKICAgICAgICAgICAgOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICB2YXIgbWFya2VyXzI5YTU0NjdmZTc0ZDQwYmNhZjhhN2VjY2ZmNTk3ZWUyID0gTC5tYXJrZXIoCiAgICAgICAgICAgIFs0NS4zMywgLTEyMS42ODIzXSwKICAgICAgICAgICAgewogICAgICAgICAgICAgICAgaWNvbjogbmV3IEwuSWNvbi5EZWZhdWx0KCksCiAgICAgICAgICAgICAgICB9CiAgICAgICAgICAgICkuYWRkVG8obWFwXzIzN2Q4ZGY4ODc5YjRmZWJiNjg1ODIxN2JiMGViOWFlKTsKICAgICAgICAKICAgIAoKICAgICAgICAgICAgICAgIHZhciBpY29uXzlhNjNkNTkzZWVlZDRjMjBhNTg5NGFhOTU3OWE2ODAwID0gTC5Bd2Vzb21lTWFya2Vycy5pY29uKHsKICAgICAgICAgICAgICAgICAgICBpY29uOiAnaW5mby1zaWduJywKICAgICAgICAgICAgICAgICAgICBpY29uQ29sb3I6ICd3aGl0ZScsCiAgICAgICAgICAgICAgICAgICAgbWFya2VyQ29sb3I6ICdyZWQnLAogICAgICAgICAgICAgICAgICAgIHByZWZpeDogJ2dseXBoaWNvbicsCiAgICAgICAgICAgICAgICAgICAgZXh0cmFDbGFzc2VzOiAnZmEtcm90YXRlLTAnCiAgICAgICAgICAgICAgICAgICAgfSk7CiAgICAgICAgICAgICAgICBtYXJrZXJfMjlhNTQ2N2ZlNzRkNDBiY2FmOGE3ZWNjZmY1OTdlZTIuc2V0SWNvbihpY29uXzlhNjNkNTkzZWVlZDRjMjBhNTg5NGFhOTU3OWE2ODAwKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwXzgwODY2Yzg3YjhhYjRlYzA5OWM0NDY1MWExM2ExOTM2ID0gTC5wb3B1cCh7bWF4V2lkdGg6ICcxMDAlJwogICAgICAgICAgICAKICAgICAgICAgICAgfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sXzY5MDc4MWM0ODZhODQ1NGM4MDQ0NzUyYmE0NDg1OWQxID0gJChgPGRpdiBpZD0iaHRtbF82OTA3ODFjNDg2YTg0NTRjODA0NDc1MmJhNDQ4NTlkMSIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+U29tZSBPdGhlciBMb2NhdGlvbjwvZGl2PmApWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfODA4NjZjODdiOGFiNGVjMDk5YzQ0NjUxYTEzYTE5MzYuc2V0Q29udGVudChodG1sXzY5MDc4MWM0ODZhODQ1NGM4MDQ0NzUyYmE0NDg1OWQxKTsKICAgICAgICAgICAgCgogICAgICAgICAgICBtYXJrZXJfMjlhNTQ2N2ZlNzRkNDBiY2FmOGE3ZWNjZmY1OTdlZTIuYmluZFBvcHVwKHBvcHVwXzgwODY2Yzg3YjhhYjRlYzA5OWM0NDY1MWExM2ExOTM2KQogICAgICAgICAgICA7CgogICAgICAgICAgICAKICAgICAgICAKPC9zY3JpcHQ+" style="position:absolute;width:100%;height:100%;left:0;top:0;border:none !important;" allowfullscreen webkitallowfullscreen mozallowfullscreen></iframe></div></div>
</div>


