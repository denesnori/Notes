### matplotlib


#### Simple bar chart from a dictionary

```plt.bar(range, [values])```

```
import matplotlib.pyplot as plt

D = { 'A': 3, 'B':6,'C':11}

plt.bar(range(len(D),D.values()))
plt.xticks(range(len(D)), list(D.keys())),

plt.show()
```
