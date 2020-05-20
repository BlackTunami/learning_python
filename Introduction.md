## Functions and Packages
### List methods
- index(), to get the index of the first element of a list that matches its input and
- count(), to get the number of times an element appears in a list.
- append(),  adds an element to the list it is called on
- remove(), removes the first element of a list that matches the input
- reverse(), reverses the order of the elements in the list it is called on.
```py
In [7]: # Create list areas
        areas = [11.25, 18.0, 20.0, 10.75, 9.50]
        
        # Use append twice to add poolhouse and garage size
        areas.append(24.5)
        areas.append(15.45)
        
        
        # Print out areas
        print(areas)
        
        
        # Reverse the orders of the elements in areas
        areas.reverse()
        
        # Print out areas
        print(areas)
[11.25, 18.0, 20.0, 10.75, 9.5, 24.5, 15.45]
[15.45, 24.5, 9.5, 10.75, 20.0, 18.0, 11.25]
```

### Import package
``import``
```py
import math
from math import radians
```

```py
import scipy
from scipy.linalg import inv as my_inv
```



