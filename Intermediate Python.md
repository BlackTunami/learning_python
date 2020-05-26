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




