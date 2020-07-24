# Intermediate Python
## 1.Matplotlib
### 导入matplotlib.pyplot画图  

```py
# Import matplotlib.pyplot as plt
import matplotlib.pyplot as plt

# Make a line plot: year on the x-axis, pop on the y-axis
plt.plot(year,pop)

# Display the plot with plt.show()
plt.show()
```
![](https://raw.githubusercontent.com/rzldasb/learning_python/200afba34d8b34198e6417c33e304ae374984eb1/DC_MD_1.1.svg)

```py
# Change the line plot below to a scatter plot
plt.scatter(gdp_cap, life_exp)

# Put the x-axis on a logarithmic scale
plt.xscale('log')

# Show plot
plt.show()
```
![](https://raw.githubusercontent.com/rzldasb/learning_python/d5eeec0546e140024c58b0ec5d36817e2481f62a/DC_MD_1.2.svg)


```py
plt.show() # 展示  
plt.clf() # 消除  
```

### 自定义横坐标纵坐标和主题标签
```py
# Basic scatter plot, log scale
plt.scatter(gdp_cap, life_exp)
plt.xscale('log') 

# Strings
xlab = 'GDP per Capita [in USD]'
ylab = 'Life Expectancy [in years]'
title = 'World Development in 2007'

# Add axis labels
plt.xlabel(xlab)
plt.ylabel(ylab)

# Add title
plt.title(title)

# After customizing, display the plot
plt.show()
```
![](https://raw.githubusercontent.com/rzldasb/learning_python/e765fd0cfb44e33d27c3c5b16147d3567035d7fa/DC_MD_1.3.svg)

### Ticks刻度
``plt.yticks([0,1,2], ["one","two","three"])``
把原来的刻度0，1，2替换成one，two，three  

```py
# Scatter plot
plt.scatter(gdp_cap, life_exp)

# Previous customizations
plt.xscale('log') 
plt.xlabel('GDP per Capita [in USD]')
plt.ylabel('Life Expectancy [in years]')
plt.title('World Development in 2007')

# Definition of tick_val and tick_lab
tick_val = [1000, 10000, 100000]
tick_lab = ['1k', '10k', '100k']

# Adapt the ticks on the x-axis
plt.xticks(tick_val,tick_lab)


# After customizing, display the plot
plt.show()
```
![](https://raw.githubusercontent.com/rzldasb/learning_python/e765fd0cfb44e33d27c3c5b16147d3567035d7fa/DC_MD_1.4.svg)


### size尺寸
plt.scatter(gdp_cap, life_exp, s = np_pop)

```py
# Import numpy as np
import numpy as np

# Store pop as a numpy array: np_pop
np_pop = np.array(pop)

# Double np_pop
np_pop = np_pop * 2

# Update: set s argument to np_pop

plt.scatter(gdp_cap, life_exp, s = np_pop)

# Previous customizations
plt.xscale('log') 
plt.xlabel('GDP per Capita [in USD]')
plt.ylabel('Life Expectancy [in years]')
plt.title('World Development in 2007')
plt.xticks([1000, 10000, 100000],['1k', '10k', '100k'])

# Display the plot
plt.show()
```

### color颜色

用字典格式设置颜色。  
```py
col = {
    'Asia':'red',
    'Europe':'green',
    'Africa':'blue',
    'Americas':'yellow',
    'Oceania':'black'
}
```

```py
# Specify c and alpha inside plt.scatter()
plt.scatter(x = gdp_cap, y = life_exp, s = np.array(pop) * 2, c = col,alpha=0.8)

# Previous customizations
plt.xscale('log') 
plt.xlabel('GDP per Capita [in USD]')
plt.ylabel('Life Expectancy [in years]')
plt.title('World Development in 2007')
plt.xticks([1000,10000,100000], ['1k','10k','100k'])

# Show the plot
plt.show()
```
![](https://raw.githubusercontent.com/rzldasb/learning_python/e765fd0cfb44e33d27c3c5b16147d3567035d7fa/DC_MD_1.5.svg)  


### text添加文本
```py
# Scatter plot
plt.scatter(x = gdp_cap, y = life_exp, s = np.array(pop) * 2, c = col, alpha = 0.8)

# Previous customizations
plt.xscale('log') 
plt.xlabel('GDP per Capita [in USD]')
plt.ylabel('Life Expectancy [in years]')
plt.title('World Development in 2007')
plt.xticks([1000,10000,100000], ['1k','10k','100k'])

# Additional customizations
plt.text(1550, 71, 'India')
plt.text(5700, 80, 'China')

# Add grid() call
plt.grid(True) 

# Show the plot
plt.show()
```


## 2. Dictionaries & Pandas 

```py
# Definition of dictionary
europe = {'spain':'madrid', 'france':'paris', 'germany':'berlin', 'norway':'oslo' }

# Print out the keys in europe
print(europe.keys())  
Output: dict_keys(['france', 'germany', 'norway', 'spain'])  

# Print out value that belongs to key 'norway'
print(europe["norway"])
Output: oslo  
```
.keys()提取key值  

删除字典值，del(world["sealand"])

```py
# Definition of dictionary
europe = {'spain':'madrid', 'france':'paris', 'germany':'bonn',
          'norway':'oslo', 'italy':'rome', 'poland':'warsaw',
          'australia':'vienna' }

# Update capital of germany
europe["germany"] = "berlin"

# Remove australia
del(europe["australia"])

# Print europe
print(europe)
```


```py
# Dictionary of dictionaries
europe = { 'spain': { 'capital':'madrid', 'population':46.77 },
           'france': { 'capital':'paris', 'population':66.03 },
           'germany': { 'capital':'berlin', 'population':80.62 },
           'norway': { 'capital':'oslo', 'population':5.084 } }


# Print out the capital of France
europe["france"]["capital"]

# Create sub-dictionary data
data={"captial":"rome","population":59.83}

# Add data to europe under key 'italy'
europe["italy"]=data

# Print europe
print(europe)
Output: {'france': {'capital': 'paris', 'population': 66.03}, 'norway': {'capital': 'oslo', 'population': 5.084}, 'italy': {'captial': 'rome', 'population': 59.83}, 'germany': {'capital': 'berlin', 'population': 80.62}, 'spain': {'capital': 'madrid', 'population': 46.77}}
```


### Pandas and DataFrame
```py
In [2]: # Pre-defined lists
        names = ['United States', 'Australia', 'Japan', 'India', 'Russia', 'Morocco', 'Egypt']
        dr =  [True, False, False, False, True, True, True]
        cpc = [809, 731, 588, 18, 200, 70, 45]
        
        # Import pandas as pd
        import pandas as pd
        
        # Create dictionary my_dict with three key:value pairs: my_dict
        my_dict={"country":names,"drives_right":dr,"cars_per_cap":cpc}
        
        # Build a DataFrame cars from my_dict: cars
        cars=pd.DataFrame(my_dict)
        
        # Print cars
        print(cars)
   cars_per_cap        country  drives_right
0           809  United States          True
1           731      Australia         False
2           588          Japan         False
3            18          India         False
4           200         Russia          True
5            70        Morocco          True
6            45          Egypt          True

<script.py> output:
       cars_per_cap        country  drives_right
    0           809  United States          True
    1           731      Australia         False
    2           588          Japan         False
    3            18          India         False
    4           200         Russia          True
    5            70        Morocco          True
    6            45          Egypt          True
```


设置行名  
```py
In [4]: import pandas as pd
        
        # Build cars DataFrame
        names = ['United States', 'Australia', 'Japan', 'India', 'Russia', 'Morocco', 'Egypt']
        dr =  [True, False, False, False, True, True, True]
        cpc = [809, 731, 588, 18, 200, 70, 45]
        cars_dict = { 'country':names, 'drives_right':dr, 'cars_per_cap':cpc }
        cars = pd.DataFrame(cars_dict,)
        print(cars)
        
        # Definition of row_labels
        row_labels = ['US', 'AUS', 'JPN', 'IN', 'RU', 'MOR', 'EG']
        
        # Specify row labels of cars
        cars.index=row_labels
        
        
        # Print cars again
        print(cars)
   cars_per_cap        country  drives_right
0           809  United States          True
1           731      Australia         False
2           588          Japan         False
3            18          India         False
4           200         Russia          True
5            70        Morocco          True
6            45          Egypt          True
     cars_per_cap        country  drives_right
US            809  United States          True
AUS           731      Australia         False
JPN           588          Japan         False
IN             18          India         False
RU            200         Russia          True
MOR            70        Morocco          True
EG             45          Egypt          True

```

```py
In [2]: # Import pandas as pd
        import pandas as pd
        
        # Import the cars.csv data: cars
        cars= pd.read_csv("cars.csv")
        
        # Print out cars
        print(cars)
  Unnamed: 0  cars_per_cap        country  drives_right
0         US           809  United States          True
1        AUS           731      Australia         False
2        JPN           588          Japan         False
3         IN            18          India         False
4         RU           200         Russia          True
5        MOR            70        Morocco          True
6         EG            45          Egypt          True
```


```py
In [1]: # Import pandas as pd
        import pandas as pd
        
        # Fix import by including index_col
        cars = pd.read_csv('cars.csv',index_col=0)
        
        # Print out cars
        print(cars)
     cars_per_cap        country  drives_right
US            809  United States          True
AUS           731      Australia         False
JPN           588          Japan         False
IN             18          India         False
RU            200         Russia          True
MOR            70        Morocco          True
EG             45          Egypt          True
```

单括号[]和双括号[[]]的区别  

```py
In [2]: # Import cars data
        import pandas as pd
        cars = pd.read_csv('cars.csv', index_col = 0)
        
        # Print out country column as Pandas Series
        print(cars["country"])
        
        # Print out country column as Pandas DataFrame
        print(cars[["country"]])
        
        # Print out DataFrame with country and drives_right columns
        print(cars[["country","drives_right"]])
US     United States
AUS        Australia
JPN            Japan
IN             India
RU            Russia
MOR          Morocco
EG             Egypt
Name: country, dtype: object
           country
US   United States
AUS      Australia
JPN          Japan
IN           India
RU          Russia
MOR        Morocco
EG           Egypt
           country  drives_right
US   United States          True
AUS      Australia         False
JPN          Japan         False
IN           India         False
RU          Russia          True
MOR        Morocco          True
EG           Egypt          True
```


数据框和series的区别没有搞懂    
```py
cars.loc[:, 'country']
cars.iloc[:, 1]

cars.loc[:, ['country','drives_right']]
cars.iloc[:, [1, 2]]
```



