# matplob
```
# plot using dot instead of line, third arguments listed it
import matplotlib.pyplot as plt
plt.plot([1, 2, 3, 4], [1, 4, 9, 16], 'ro')
plt.axis([0, 6, 0, 20])
plt.show()
```

```
# plot 3 in same pic
import numpy as np

# evenly sampled time at 200ms intervals
t = np.arange(0., 5., 0.2)

# red dashes, blue squares and green triangles
plt.plot(t, t, 'r--', t, t**2, 'bs', t, t**3, 'g^')
plt.show()
```

```
names = ['group_a', 'group_b', 'group_c']
values = [1, 10, 100]

plt.figure(figsize=(9, 3))

plt.subplot(131)
plt.bar(names, values)
plt.subplot(132)
plt.scatter(names, values)
plt.subplot(133)
plt.plot(names, values)
plt.suptitle('Categorical Plotting')
plt.show()
```

```
# following lines is a 2D object that get the handle of plt, you can use it to set 
lines = plt.plot([1, 2, 3])
plt.setp(lines)
#---> check what is settable attribute 

# add text in the figure, 
mu, sigma = 100, 15
#𝜎𝑖=15----> sigma is 𝜎
plt.text(60, .025, r'$\mu=100,\ \sigma=15$')
```

```
# use annotate to attach text in the figure
# xy is the x and y location of the fig that you want to add text
# xytext is the real text location 
# "local max" is the text you added in the figure
# arrowprops is the arrow shape

plt.annotate('local max', xy=(2, 1), xytext=(3, 1.5),
             arrowprops=dict(facecolor='black', shrink=0.05),
             )
             
             
```

```
# scare the y using log
plt.yscale('log')
# show the grid
plt.grid(True)
```

```
# add legend in the pic
plt.plot(x, x, label='linear')
plt.plot(x, x**2, label='quadratic')
plt.plot(x, x**3, label='cubic')
plt.legend()
plt.show()
```

```
# wrap the plot in your function

def my_plotter(ax, data1, data2, param_dict):
    """
    A helper function to make a graph

    Parameters
    ----------
    ax : Axes
        The axes to draw to

    data1 : array
       The x data

    data2 : array
       The y data

    param_dict : dict
       Dictionary of kwargs to pass to ax.plot

    Returns
    -------
    out : list
        list of artists added
    """
    out = ax.plot(data1, data2, **param_dict)
    return out

# which you would then use as:

data1, data2, data3, data4 = np.random.randn(4, 100)
fig, ax = plt.subplots(1, 1)
my_plotter(ax, data1, data2, {'marker': 'x'})

```
```

```
