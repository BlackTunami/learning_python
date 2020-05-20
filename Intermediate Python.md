# Intermediate Python
## 1.Matplotlib
导入matplotlib.pyplot画图  

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


