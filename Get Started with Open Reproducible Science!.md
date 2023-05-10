---

# Get started with open reproducible science!

[Open reproducible science](https://www.earthdatascience.org/courses/intro-to-earth-data-science/open-reproducible-science/get-started-open-reproducible-science/) makes scientific methods, data and outcomes available to everyone. That means that *everyone* who wants should be able to **find**, **read**, **understand**, and **run** your workflows for themselves.

<img alt-text="Components of open science - accessible, reproducible, inclusive" src="https://www.earthdata.nasa.gov/s3fs-public/2021-11/Circle_Diagram_UPDATE_2.jpg?VersionId=pFRniRpjtgc_MEXUJKi9_sXLoMsSX.pB" width=500 />

 > Image from https://www.earthdata.nasa.gov/esds/open-science/oss-for-eso-workshops

Few if any science projects are 100% open and reproducible (yet!). However, members of the open science community have developed open source tools and practices that can help you move toward that goal. You will learn about many of those tools in [the Intro to Earth Data Science textbook](https://www.earthdatascience.org/courses/intro-to-earth-data-science/). Don't worry about learning all the tools at once -- we've picked a few for you to get started with.

I can write clean code by:
  * Don't modify raw data and keep original data and results separate.
  * Include a workflow with comments in markdown that explain the workflow.
  * Use a well known programming language like Python and store explanations in a place like Jupyter Notebooks or a Readme file in GitHub.



Advantages of clean code include:
  * Funders can see and better understand your work.
  * It can be time-saving for others who may use the code.
  * Others can understand your workflow and reproduce your project from you code.
  


```python
# pandas_library_import
import pandas as pd

pd.DataFrame()
```




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
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
</div>



Once you have run the cell above and imported `pandas`, **run the cell below**. It is a test cell that will tell you if you completed the task successfully. If a test cell isn't working the way you expect, check that you ran your code **immediately before** running the test.


```python
# DO NOT MODIFY THIS TEST CELL
points = 0
try:
    pd.DataFrame()
    points += 5
    print('\u2705 Great work! You correctly imported the pandas library.')
except:
    print('\u274C Oops - pandas was not imported correctly.')
print('You earned {} of 5 points for importing pandas'.format(points))
```

    ✅ Great work! You correctly imported the pandas library.
    You earned 5 of 5 points for importing pandas





1. Climate at a Glance, Rapid City, South Dakota, maximum daily average temperature:

2. The data from the Climate at a Glance data sources is taken at research facilities in Rapid City, SD.  The research facilities are part of the National Oceanic and Atmospheric Administration (NOAA) and the information collected is stored and diseminated by the National Centers for Environmental Information (NCEI).  The information is collected at Automated Surface Observing System (ASOS) stations using sensors and sometimes human recordings.   Maximum daily average temperatures are the combination of daily average temperature combined with the annual maximum temperature.

3. Citing
   
    NOAA National Centers for Environmental Information, Climate at a Glance: City Haywoods, published April 2023, retrieved on April 20, 2023 from https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/city/haywood

**YOUR DATA DESCRIPTION AND CITATION HERE**


```python
rapid_city_max_temp_F = ("https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance"
                         "/city/time-series/USW00024090/tmax/ann/2/1949-2023.csv")

rapid_city_max_temp_F
```




    'https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/city/time-series/USW00024090/tmax/ann/2/1949-2023.csv'




```python
# DO NOT MODIFY THIS TEST CELL
resp_url = _
points = 0

if type(resp_url)==str:
    points += 3
    print('\u2705 Great work! You correctly called your url variable.')
else:
    print('\u274C Oops - your url variable was not called correctly.')

if len(resp_url)==117:
    points += 3
    print('\u2705 Great work! Your url is the correct length.')
else:
    print('\u274C Oops - your url variable is not the correct length.')

print('You earned {} of 6 points for defining a url variable'.format(points))
```

    ✅ Great work! You correctly called your url variable.
    ✅ Great work! Your url is the correct length.
    You earned 6 of 6 points for defining a url variable



```python
#download
rapid_city_df = pd.read_csv(rapid_city_max_temp_F, header = 3, names = ['years', 'temp'])
rapid_city_df


```




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
      <th>years</th>
      <th>temp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>194912</td>
      <td>58.4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>195012</td>
      <td>55.6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>195112</td>
      <td>54.6</td>
    </tr>
    <tr>
      <th>3</th>
      <td>195212</td>
      <td>59.4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>195312</td>
      <td>59.8</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>69</th>
      <td>201812</td>
      <td>57.2</td>
    </tr>
    <tr>
      <th>70</th>
      <td>201912</td>
      <td>54.7</td>
    </tr>
    <tr>
      <th>71</th>
      <td>202012</td>
      <td>61.8</td>
    </tr>
    <tr>
      <th>72</th>
      <td>202112</td>
      <td>62.1</td>
    </tr>
    <tr>
      <th>73</th>
      <td>202212</td>
      <td>60.9</td>
    </tr>
  </tbody>
</table>
<p>74 rows × 2 columns</p>
</div>




```python
# DO NOT MODIFY THIS TEST CELL
tmax_df_resp = _
points = 0

if isinstance(tmax_df_resp, pd.DataFrame):
    points += 1
    print('\u2705 Great work! You called a DataFrame.')
else:
    print('\u274C Oops - make sure to call your DataFrame for testing.')
    
summary = [round(val, 2) for val in tmax_df_resp.mean().values]
if summary == [198562.0, 59.04]:
    points += 4
    print('\u2705 Great work! You correctly downloaded data.')
else:
    print('\u274C Oops - your data are not correct.')
print('You earned {} of 5 points for downloading data'.format(points))
```

    ✅ Great work! You called a DataFrame.
    ❌ Oops - your data are not correct.
    You earned 1 of 5 points for downloading data


  > HINT: Check out the `type()` function below - you can use it to check that your data is now in `DataFrame` type object


```python
# Check that the data was imported into a pandas DataFrame
type(rapid_city_df)
```




    pandas.core.frame.DataFrame




```python
# ncei has wacky years
rapid_city_df.iloc[:,0] = rapid_city_df.iloc[:,0] // 100
rapid_city_df

```




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
      <th>years</th>
      <th>temp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1949</td>
      <td>58.4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1950</td>
      <td>55.6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1951</td>
      <td>54.6</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1952</td>
      <td>59.4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1953</td>
      <td>59.8</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>69</th>
      <td>2018</td>
      <td>57.2</td>
    </tr>
    <tr>
      <th>70</th>
      <td>2019</td>
      <td>54.7</td>
    </tr>
    <tr>
      <th>71</th>
      <td>2020</td>
      <td>61.8</td>
    </tr>
    <tr>
      <th>72</th>
      <td>2021</td>
      <td>62.1</td>
    </tr>
    <tr>
      <th>73</th>
      <td>2022</td>
      <td>60.9</td>
    </tr>
  </tbody>
</table>
<p>74 rows × 2 columns</p>
</div>




```python
# DO NOT MODIFY THIS TEST CELL
tmax_df_resp = _
points = 0

if isinstance(tmax_df_resp, pd.DataFrame):
    points += 1
    print('\u2705 Great work! You called a DataFrame.')
else:
    print('\u274C Oops - make sure to call your DataFrame for testing.')
    
summary = [round(val, 2) for val in tmax_df_resp.mean().values]
if summary == [1985.5, 59.04]:
    points += 4
    print('\u2705 Great work! You correctly cleaned up years.')
else:
    print('\u274C Oops - your data are not correct.')
print('You earned {} of 5 points for cleaning up years'.format(points))
```

    ✅ Great work! You called a DataFrame.
    ❌ Oops - your data are not correct.
    You earned 1 of 5 points for cleaning up years


<img src="https://static.thenounproject.com/png/3842781-200.png" width=20 style="float: left; padding: 3px" /> Want an EXTRA CHALLENGE? Modify the code to be **more expressive**.

Rewrite the code below to select columns by **name** instead of by **index**. You might find the [pandas User Guide section on slicing and dicing](https://pandas.pydata.org/docs/user_guide/indexing.html) to be useful. However - don't worry if you can't figure this out yet! We're going to talk a lot about how to use pandas `DataFrame`s. 

YOUR ANSWER HERE


```python
#convert to celcius
rapid_city_df.iloc[:,1] = (rapid_city_df.iloc[:,1] - 32) * 5 / 9
rapid_city_df

```




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
      <th>years</th>
      <th>temp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1949</td>
      <td>14.666667</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1950</td>
      <td>13.111111</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1951</td>
      <td>12.555556</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1952</td>
      <td>15.222222</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1953</td>
      <td>15.444444</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>69</th>
      <td>2018</td>
      <td>14.000000</td>
    </tr>
    <tr>
      <th>70</th>
      <td>2019</td>
      <td>12.611111</td>
    </tr>
    <tr>
      <th>71</th>
      <td>2020</td>
      <td>16.555556</td>
    </tr>
    <tr>
      <th>72</th>
      <td>2021</td>
      <td>16.722222</td>
    </tr>
    <tr>
      <th>73</th>
      <td>2022</td>
      <td>16.055556</td>
    </tr>
  </tbody>
</table>
<p>74 rows × 2 columns</p>
</div>




```python
# DO NOT MODIFY THIS TEST CELL
tmax_df_resp = _
points = 0

if isinstance(tmax_df_resp, pd.DataFrame):
    points += 1
    print('\u2705 Great work! You called a DataFrame.')
else:
    print('\u274C Oops - make sure to call your DataFrame for testing.')
    
summary = [round(val, 2) for val in tmax_df_resp.mean().values]
if summary == [1985.5, 15.02]:
    points += 4
    print('\u2705 Great work! You correctly converted to Celcius.')
else:
    print('\u274C Oops - your data are not correct.')
print('You earned {} of 5 points for converting to Celcius'.format(points))
```

    ✅ Great work! You called a DataFrame.
    ❌ Oops - your data are not correct.
    You earned 1 of 5 points for converting to Celcius


<img src="https://static.thenounproject.com/png/3842781-200.png" width=20 style="float: left; padding: 3px" /> Want an **EXTRA CHALLENGE**?
  1. As you did above, rewrite the code to be more expressive
  2. Using the code below as a framework, write and apply a **function** that converts to Celcius.
     > **Functions** let you reuse code you have already written
  
  3. You should also rewrite this function name to be more expressive.
  
        ```python
        def convert(temperature):
            """Convert temperature to Celcius"""
            return temperature # Put your equation in here

        dataframe['temp_c'] = dataframe['temp_f'].apply(convert)
        ```


```python
#plotting and labeling axes
rapid_city_df.plot(x='years', y='temp', title="Maximum " 
                   "Annual Temperature in Rapid City, SD",
                   ylabel="Temperature in Celcius", xlabel="Years", legend=False)
```




    <AxesSubplot:title={'center':'Maximum Annual Temperature in Rapid City, SD'}, xlabel='Years', ylabel='Temperature in Celcius'>




    
![png](Get%20Started%20with%20Open%20Reproducible%20Science%21_files/Get%20Started%20with%20Open%20Reproducible%20Science%21_22_1.png)
    


**THIS ISN'T THE END! Don't forget to complete the next task where you will describe your plot**
    
<img src="https://www.nps.gov/pais/learn/nature/images/NPS-KempsRidley-Hatchlings.JPG" height=150 style="padding: 1em; border-style: solid; border-color: grey;" />

> Image source: https://www.nps.gov/pais/learn/nature/hatchlingreleases.htm

<img src="https://static.thenounproject.com/png/3842781-200.png" width=20 style="float: left; padding: 3px" /> Want an **EXTRA CHALLENGE**?

There are many other things you can do to customize your plot. Take a look at the [pandas plotting galleries](https://pandas.pydata.org/docs/user_guide/visualization.html) and the [documentation of plot](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.plot.html) to see if there's other changes you want to make to your plot. Some possibilities include:
  * Remove the legend since there's only one data series
  * Increase the figure size
  * Increase the font size
  * Change the colors
  * Use a bar graph instead (usually we use lines for time series, but since this is annual it could go either way)
  * Add a trend line

## YOUR RAPID CITY PLOT HEADLINE HERE
Describe your plot in this cell in 2-3 sentences

The daily high is on the rise in Rapid City, SD.

**THIS ISN'T THE END EITHER! Don't forget to reproduce your analysis in a new location!**

<img src="https://static.independent.co.uk/s3fs-public/thumbnails/image/2008/12/26/20/107000.jpg" height=150 style="padding: 1em; border-style: solid; border-color: grey;" >

> Image source: https://www.independent.co.uk/climate-change/news/by-the-left-quick-march-the-emperor-penguins-migration-1212420.html

## Your turn: pick a new location and/or measurement to plot
Below, recreate the workflow you just did in a place that interests you OR with a different measurement. See the instructions above fore how to get your URL. You will need to make your own new Markdown and Code cells below this one.


```python
# pandas_library_import
import pandas as pd

pd.DataFrame()
```




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
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
</div>




```python
#Accessing climate data for portland, maine
portland_ME_climate_data = ("https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/city/haywood/USH00176905/tmax/12/data.csv")
```


```python
#Creating and Defining Portland Maine Data Frame
portland_ME_df = pd.read_csv(portland_ME_climate_data, header = 3, names = ['year', 'month', 'temp'])
portland_ME_df
```




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
      <th>year</th>
      <th>month</th>
      <th>temp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1895</td>
      <td>1</td>
      <td>-99.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1895</td>
      <td>2</td>
      <td>29.7</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1895</td>
      <td>3</td>
      <td>32.2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1895</td>
      <td>4</td>
      <td>36.9</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1895</td>
      <td>5</td>
      <td>42.2</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1487</th>
      <td>2022</td>
      <td>12</td>
      <td>58.4</td>
    </tr>
    <tr>
      <th>1488</th>
      <td>2023</td>
      <td>1</td>
      <td>39.5</td>
    </tr>
    <tr>
      <th>1489</th>
      <td>2023</td>
      <td>2</td>
      <td>38.7</td>
    </tr>
    <tr>
      <th>1490</th>
      <td>2023</td>
      <td>3</td>
      <td>40.3</td>
    </tr>
    <tr>
      <th>1491</th>
      <td>2023</td>
      <td>4</td>
      <td>43.9</td>
    </tr>
  </tbody>
</table>
<p>1492 rows × 3 columns</p>
</div>




```python
#delete rows with faulty data
print(portland_ME_df.drop(0,axis=0,inplace=True))
```

    None



```python
#convert to celcius
portland_ME_df.iloc[:,2]=(portland_ME_df.iloc[:,2] - 32) * 5 / 9
portland_ME_df

```




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
      <th>year</th>
      <th>month</th>
      <th>temp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>1895</td>
      <td>2</td>
      <td>-1.277778</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1895</td>
      <td>3</td>
      <td>0.111111</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1895</td>
      <td>4</td>
      <td>2.722222</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1895</td>
      <td>5</td>
      <td>5.666667</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1895</td>
      <td>6</td>
      <td>8.388889</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1487</th>
      <td>2022</td>
      <td>12</td>
      <td>14.666667</td>
    </tr>
    <tr>
      <th>1488</th>
      <td>2023</td>
      <td>1</td>
      <td>4.166667</td>
    </tr>
    <tr>
      <th>1489</th>
      <td>2023</td>
      <td>2</td>
      <td>3.722222</td>
    </tr>
    <tr>
      <th>1490</th>
      <td>2023</td>
      <td>3</td>
      <td>4.611111</td>
    </tr>
    <tr>
      <th>1491</th>
      <td>2023</td>
      <td>4</td>
      <td>6.611111</td>
    </tr>
  </tbody>
</table>
<p>1491 rows × 3 columns</p>
</div>




```python
#calculate the average yearly temps
print(portland_ME_df.groupby('year').mean())
```

          month       temp
    year                  
    1895    7.0   8.166667
    1896    6.5   7.148148
    1897    6.5   8.101852
    1898    6.5   8.263889
    1899    6.5   7.962963
    ...     ...        ...
    2019    6.5   8.861111
    2020    6.5  10.916667
    2021    6.5  10.041667
    2022    6.5   9.907407
    2023    2.5   4.777778
    
    [125 rows x 2 columns]



```python

```


```python
portland_ME_df.plot(x='year', y='temp', title="Average Maximum " 
                   "Annual Temperature in Portland, ME Since 1895",
                   ylabel=("Temperature ($^\circ$C)"), xlabel="Years",
                   legend=False)
```




    <AxesSubplot:title={'center':'Average Maximum Annual Temperature in Portland, ME Since 1895'}, xlabel='Years', ylabel='Temperature ($^\\circ$C)'>




    
![png](Get%20Started%20with%20Open%20Reproducible%20Science%21_files/Get%20Started%20with%20Open%20Reproducible%20Science%21_35_1.png)
    



```python
# pandas_library_import
import pandas as pd

#Accessing climate data for portland, maine
portland_ME_climate_data = ("https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/city/haywood/USH00176905/tmax/12/data.csv")

pd.DataFrame()

#Creating and Defining Portland Maine Data Frame
portland_ME_df = pd.read_csv(portland_ME_climate_data, header = 3, names = ['year', 'month', 'temp'])
portland_ME_df
```




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
      <th>year</th>
      <th>month</th>
      <th>temp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1895</td>
      <td>1</td>
      <td>-99.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1895</td>
      <td>2</td>
      <td>29.7</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1895</td>
      <td>3</td>
      <td>32.2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1895</td>
      <td>4</td>
      <td>36.9</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1895</td>
      <td>5</td>
      <td>42.2</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1487</th>
      <td>2022</td>
      <td>12</td>
      <td>58.4</td>
    </tr>
    <tr>
      <th>1488</th>
      <td>2023</td>
      <td>1</td>
      <td>39.5</td>
    </tr>
    <tr>
      <th>1489</th>
      <td>2023</td>
      <td>2</td>
      <td>38.7</td>
    </tr>
    <tr>
      <th>1490</th>
      <td>2023</td>
      <td>3</td>
      <td>40.3</td>
    </tr>
    <tr>
      <th>1491</th>
      <td>2023</td>
      <td>4</td>
      <td>43.9</td>
    </tr>
  </tbody>
</table>
<p>1492 rows × 3 columns</p>
</div>



## Average highs have risen slightly in the last 130 years in Portland, Maine.
