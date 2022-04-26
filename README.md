# vg-stats - ["The Notebook"](./vg-sales.ipynb)
---
jupyter:
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
  language_info:
    codemirror_mode:
      name: ipython
      version: 3
    file_extension: .py
    mimetype: text/x-python
    name: python
    nbconvert_exporter: python
    pygments_lexer: ipython3
    version: 3.7.12
  nbformat: 4
  nbformat_minor: 5
  papermill:
    default_parameters: {}
    duration: 11.307572
    end_time: "2022-04-26T04:26:05.252862"
    environment_variables: {}
    input_path: \_\_notebook\_\_.ipynb
    output_path: \_\_notebook\_\_.ipynb
    parameters: {}
    start_time: "2022-04-26T04:25:53.94529"
    version: 2.3.4
---

::: {.cell .markdown}
`<a href="https://www.kaggle.com/code/abedalqaderalkhatib/notebook6b2eba3570?scriptVersionId=94018446" target="_blank">`{=html}`<img align="left" alt="Kaggle" title="Open in Kaggle" src="https://kaggle.com/static/images/open-in-kaggle.svg">`{=html}`</a>`{=html}
:::

::: {.cell .markdown _cell_guid="b1076dfc-b9ad-4769-8c92-a6c4dae69d19" _uuid="8f2839f25d086af736a60e9eeb907d3b93b6e0e5" papermill="{\"status\":\"completed\",\"duration\":1.4984e-2,\"end_time\":\"2022-04-26T04:26:03.913222\",\"exception\":false,\"start_time\":\"2022-04-26T04:26:03.898238\"}" tags="[]"}
# Data Analysis With Pandas

## Data Set Name: Video Game Sales

**Read the data**
:::

::: {.cell .code execution_count="1" execution="{\"iopub.status.busy\":\"2022-04-26T04:26:03.942611Z\",\"iopub.status.idle\":\"2022-04-26T04:26:04.026684Z\",\"iopub.execute_input\":\"2022-04-26T04:26:03.943071Z\",\"shell.execute_reply\":\"2022-04-26T04:26:04.025787Z\"}" papermill="{\"status\":\"completed\",\"duration\":0.101969,\"end_time\":\"2022-04-26T04:26:04.029161\",\"exception\":false,\"start_time\":\"2022-04-26T04:26:03.927192\"}" tags="[]"}
``` {.python}
import numpy as np
import pandas as pd

full_data=pd.read_csv("../input/vgsales/vgsales.csv")
data=full_data[full_data['Global_Sales']*1000000 > 10000]
```
:::

::: {.cell .markdown papermill="{\"status\":\"completed\",\"duration\":1.479e-2,\"end_time\":\"2022-04-26T04:26:04.059082\",\"exception\":false,\"start_time\":\"2022-04-26T04:26:04.044292\"}" tags="[]"}
### Q1: Which Company is the most Common Video Game publishe
:::

::: {.cell .code execution_count="2" execution="{\"iopub.status.busy\":\"2022-04-26T04:26:04.089041Z\",\"iopub.status.idle\":\"2022-04-26T04:26:04.101074Z\",\"iopub.execute_input\":\"2022-04-26T04:26:04.089315Z\",\"shell.execute_reply\":\"2022-04-26T04:26:04.099968Z\"}" papermill="{\"status\":\"completed\",\"duration\":3.0463e-2,\"end_time\":\"2022-04-26T04:26:04.104061\",\"exception\":false,\"start_time\":\"2022-04-26T04:26:04.073598\"}" tags="[]"}
``` {.python}
most_common_publisher = data['Publisher'].value_counts().idxmax()
print(str(most_common_publisher))
```

::: {.output .stream .stdout}
    Electronic Arts
:::
:::

::: {.cell .markdown papermill="{\"status\":\"completed\",\"duration\":1.5074e-2,\"end_time\":\"2022-04-26T04:26:04.135878\",\"exception\":false,\"start_time\":\"2022-04-26T04:26:04.120804\"}" tags="[]"}
### Q2: What's the most common platform?
:::

::: {.cell .code execution_count="3" execution="{\"iopub.status.busy\":\"2022-04-26T04:26:04.167268Z\",\"iopub.status.idle\":\"2022-04-26T04:26:04.175931Z\",\"iopub.execute_input\":\"2022-04-26T04:26:04.16764Z\",\"shell.execute_reply\":\"2022-04-26T04:26:04.175082Z\"}" papermill="{\"status\":\"completed\",\"duration\":2.7311e-2,\"end_time\":\"2022-04-26T04:26:04.178421\",\"exception\":false,\"start_time\":\"2022-04-26T04:26:04.15111\"}" tags="[]"}
``` {.python}
most_common_platform = data['Platform'].value_counts().idxmax()
print(str(most_common_platform))

```

::: {.output .stream .stdout}
    PS2
:::
:::

::: {.cell .markdown papermill="{\"status\":\"completed\",\"duration\":1.5597e-2,\"end_time\":\"2022-04-26T04:26:04.209195\",\"exception\":false,\"start_time\":\"2022-04-26T04:26:04.193598\"}" tags="[]"}
### Q3: What about the most common genre?
:::

::: {.cell .code execution_count="4" execution="{\"iopub.status.busy\":\"2022-04-26T04:26:04.241084Z\",\"iopub.status.idle\":\"2022-04-26T04:26:04.250259Z\",\"iopub.execute_input\":\"2022-04-26T04:26:04.241376Z\",\"shell.execute_reply\":\"2022-04-26T04:26:04.248846Z\"}" papermill="{\"status\":\"completed\",\"duration\":2.8841e-2,\"end_time\":\"2022-04-26T04:26:04.253096\",\"exception\":false,\"start_time\":\"2022-04-26T04:26:04.224255\"}" tags="[]"}
``` {.python}
most_common_genre = data['Genre'].value_counts().idxmax()
print(str(most_common_genre))
```

::: {.output .stream .stdout}
    Action
:::
:::

::: {.cell .markdown papermill="{\"status\":\"completed\",\"duration\":1.4544e-2,\"end_time\":\"2022-04-26T04:26:04.28284\",\"exception\":false,\"start_time\":\"2022-04-26T04:26:04.268296\"}" tags="[]"}
### Q4: What are the top 20 highest grossing games?
:::

::: {.cell .code execution_count="5" execution="{\"iopub.status.busy\":\"2022-04-26T04:26:04.316185Z\",\"iopub.status.idle\":\"2022-04-26T04:26:04.330247Z\",\"iopub.execute_input\":\"2022-04-26T04:26:04.316714Z\",\"shell.execute_reply\":\"2022-04-26T04:26:04.329428Z\"}" papermill="{\"status\":\"completed\",\"duration\":3.3791e-2,\"end_time\":\"2022-04-26T04:26:04.33285\",\"exception\":false,\"start_time\":\"2022-04-26T04:26:04.299059\"}" tags="[]"}
``` {.python}
top_twenty_highest_grossing_games = data[['Name', 'Global_Sales']].sort_values(['Global_Sales'], ascending=False).head(20)

print(str(top_twenty_highest_grossing_games))
```

::: {.output .stream .stdout}
                                                Name  Global_Sales
    0                                     Wii Sports         82.74
    1                              Super Mario Bros.         40.24
    2                                 Mario Kart Wii         35.82
    3                              Wii Sports Resort         33.00
    4                       Pokemon Red/Pokemon Blue         31.37
    5                                         Tetris         30.26
    6                          New Super Mario Bros.         30.01
    7                                       Wii Play         29.02
    8                      New Super Mario Bros. Wii         28.62
    9                                      Duck Hunt         28.31
    10                                    Nintendogs         24.76
    11                                 Mario Kart DS         23.42
    12                   Pokemon Gold/Pokemon Silver         23.10
    13                                       Wii Fit         22.72
    14                                  Wii Fit Plus         22.00
    15                            Kinect Adventures!         21.82
    16                            Grand Theft Auto V         21.40
    17                 Grand Theft Auto: San Andreas         20.81
    18                             Super Mario World         20.61
    19  Brain Age: Train Your Brain in Minutes a Day         20.22
:::
:::

::: {.cell .markdown papermill="{\"status\":\"completed\",\"duration\":1.5936e-2,\"end_time\":\"2022-04-26T04:26:04.364858\",\"exception\":false,\"start_time\":\"2022-04-26T04:26:04.348922\"}" tags="[]"}
### Q5: For North American video game sales, what's the median?
:::

::: {.cell .code execution_count="6" execution="{\"iopub.status.busy\":\"2022-04-26T04:26:04.40018Z\",\"iopub.status.idle\":\"2022-04-26T04:26:04.431897Z\",\"iopub.execute_input\":\"2022-04-26T04:26:04.400552Z\",\"shell.execute_reply\":\"2022-04-26T04:26:04.430835Z\"}" papermill="{\"status\":\"completed\",\"duration\":5.2833e-2,\"end_time\":\"2022-04-26T04:26:04.434287\",\"exception\":false,\"start_time\":\"2022-04-26T04:26:04.381454\"}" tags="[]"}
``` {.python}
na_median = data['NA_Sales'].median()
data.iloc[(data['NA_Sales']- na_median).abs().argsort()[:11]]
```

::: {.output .execute_result execution_count="6"}
```{=html}
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
      <th>Rank</th>
      <th>Name</th>
      <th>Platform</th>
      <th>Year</th>
      <th>Genre</th>
      <th>Publisher</th>
      <th>NA_Sales</th>
      <th>EU_Sales</th>
      <th>JP_Sales</th>
      <th>Other_Sales</th>
      <th>Global_Sales</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>7831</th>
      <td>7833</td>
      <td>IL-2 Sturmovik: Birds of Prey</td>
      <td>PSP</td>
      <td>2009.0</td>
      <td>Simulation</td>
      <td>505 Games</td>
      <td>0.08</td>
      <td>0.07</td>
      <td>0.0</td>
      <td>0.04</td>
      <td>0.19</td>
    </tr>
    <tr>
      <th>3186</th>
      <td>3188</td>
      <td>SingStar Queen</td>
      <td>PS2</td>
      <td>2009.0</td>
      <td>Misc</td>
      <td>Sony Computer Entertainment</td>
      <td>0.08</td>
      <td>0.12</td>
      <td>0.0</td>
      <td>0.44</td>
      <td>0.63</td>
    </tr>
    <tr>
      <th>9088</th>
      <td>9090</td>
      <td>Mary-Kate and Ashley: Winners Circle</td>
      <td>PS</td>
      <td>2001.0</td>
      <td>Action</td>
      <td>Acclaim Entertainment</td>
      <td>0.08</td>
      <td>0.05</td>
      <td>0.0</td>
      <td>0.01</td>
      <td>0.14</td>
    </tr>
    <tr>
      <th>10269</th>
      <td>10271</td>
      <td>The Scorpion King: Rise of the Akkadian</td>
      <td>GC</td>
      <td>2002.0</td>
      <td>Action</td>
      <td>Universal Interactive</td>
      <td>0.08</td>
      <td>0.02</td>
      <td>0.0</td>
      <td>0.00</td>
      <td>0.11</td>
    </tr>
    <tr>
      <th>10762</th>
      <td>10764</td>
      <td>Heatseeker</td>
      <td>Wii</td>
      <td>2007.0</td>
      <td>Action</td>
      <td>Codemasters</td>
      <td>0.08</td>
      <td>0.00</td>
      <td>0.0</td>
      <td>0.01</td>
      <td>0.10</td>
    </tr>
    <tr>
      <th>10262</th>
      <td>10264</td>
      <td>SimAnimals Africa</td>
      <td>DS</td>
      <td>2009.0</td>
      <td>Simulation</td>
      <td>Electronic Arts</td>
      <td>0.08</td>
      <td>0.02</td>
      <td>0.0</td>
      <td>0.01</td>
      <td>0.11</td>
    </tr>
    <tr>
      <th>10260</th>
      <td>10262</td>
      <td>Bust-A-Move DS</td>
      <td>DS</td>
      <td>2005.0</td>
      <td>Puzzle</td>
      <td>505 Games</td>
      <td>0.08</td>
      <td>0.02</td>
      <td>0.0</td>
      <td>0.01</td>
      <td>0.11</td>
    </tr>
    <tr>
      <th>10255</th>
      <td>10257</td>
      <td>X-Men: Next Dimension</td>
      <td>XB</td>
      <td>2002.0</td>
      <td>Fighting</td>
      <td>Activision</td>
      <td>0.08</td>
      <td>0.02</td>
      <td>0.0</td>
      <td>0.00</td>
      <td>0.11</td>
    </tr>
    <tr>
      <th>10254</th>
      <td>10256</td>
      <td>NHL Rivals 2004</td>
      <td>XB</td>
      <td>2003.0</td>
      <td>Sports</td>
      <td>Microsoft Game Studios</td>
      <td>0.08</td>
      <td>0.02</td>
      <td>0.0</td>
      <td>0.00</td>
      <td>0.11</td>
    </tr>
    <tr>
      <th>10253</th>
      <td>10255</td>
      <td>Outlaw Golf: Nine Holes of Christmas</td>
      <td>XB</td>
      <td>2002.0</td>
      <td>Sports</td>
      <td>Simon &amp; Schuster Interactive</td>
      <td>0.08</td>
      <td>0.02</td>
      <td>0.0</td>
      <td>0.00</td>
      <td>0.11</td>
    </tr>
    <tr>
      <th>8141</th>
      <td>8143</td>
      <td>Pirates: Hunt For Blackbeard's Booty</td>
      <td>Wii</td>
      <td>2008.0</td>
      <td>Adventure</td>
      <td>Activision</td>
      <td>0.08</td>
      <td>0.08</td>
      <td>0.0</td>
      <td>0.02</td>
      <td>0.18</td>
    </tr>
  </tbody>
</table>
</div>
```
:::
:::

::: {.cell .markdown papermill="{\"status\":\"completed\",\"duration\":1.8161e-2,\"end_time\":\"2022-04-26T04:26:04.468743\",\"exception\":false,\"start_time\":\"2022-04-26T04:26:04.450582\"}" tags="[]"}
### Q6: For the top-selling game of all time, how many standard deviations above/below the mean are its sales for North America?
:::

::: {.cell .code execution_count="7" execution="{\"iopub.status.busy\":\"2022-04-26T04:26:04.504703Z\",\"iopub.status.idle\":\"2022-04-26T04:26:04.515458Z\",\"iopub.execute_input\":\"2022-04-26T04:26:04.505049Z\",\"shell.execute_reply\":\"2022-04-26T04:26:04.513983Z\"}" papermill="{\"status\":\"completed\",\"duration\":3.1353e-2,\"end_time\":\"2022-04-26T04:26:04.517694\",\"exception\":false,\"start_time\":\"2022-04-26T04:26:04.486341\"}" tags="[]"}
``` {.python}
def zscore(s):
    return (s - np.mean(s)) / np.std(s)
zscore(data['NA_Sales']).head(1)
```

::: {.output .execute_result execution_count="7"}
    0    49.618664
    Name: NA_Sales, dtype: float64
:::
:::

::: {.cell .markdown papermill="{\"status\":\"completed\",\"duration\":1.8091e-2,\"end_time\":\"2022-04-26T04:26:04.553217\",\"exception\":false,\"start_time\":\"2022-04-26T04:26:04.535126\"}" tags="[]"}
### Q7: The Nintendo Wii seems to have outdone itself with games. How does its average number of sales compare with all of the other platforms? {#q7-the-nintendo-wii-seems-to-have-outdone-itself-with-games-how-does-its-average-number-of-sales-compare-with-all-of-the-other-platforms}
:::

::: {.cell .code execution_count="8" execution="{\"iopub.status.busy\":\"2022-04-26T04:26:04.590494Z\",\"iopub.status.idle\":\"2022-04-26T04:26:04.61007Z\",\"iopub.execute_input\":\"2022-04-26T04:26:04.590818Z\",\"shell.execute_reply\":\"2022-04-26T04:26:04.609233Z\"}" papermill="{\"status\":\"completed\",\"duration\":3.9854e-2,\"end_time\":\"2022-04-26T04:26:04.612055\",\"exception\":false,\"start_time\":\"2022-04-26T04:26:04.572201\"}" tags="[]"}
``` {.python}
data.groupby(data['Platform'] == 'Wii')['Global_Sales'].mean()
```

::: {.output .execute_result execution_count="8"}
    Platform
    False    0.543983
    True     0.714830
    Name: Global_Sales, dtype: float64
:::
:::
