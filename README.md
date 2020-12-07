
from collections import Counter 
import matplotlib.pyplot as plt

STEPS = 5

freq_dist = {'banana': 5,
             'melon': 7,
             'watermelon': 2,
             'apple': 6,
             'lime': 5,
             'orange': 16,
             'yuval the king': 100,
             'pineapple': 8,
             'strawberry': 17,
             'blueberry': 11
             }

k = Counter(freq_dist)
reqeusted_dict = {i[0] : i[1] for i in k.most_common(STEPS)}

plt.style.use('seaborn-pastel')

ggplot,tableau-colorblind10

dict_sizing = {0: (0.55, 0.87, 40, -15),
               1: (0.40, 0.65, 32.5, 15),
               2: (0.625, 0.48, 25, -12.5),
               3: (0.475, 0.345, 17.5, 10),
               4: (0.55, 0.20, 11.25, 0)}

for i in range(STEPS):
    plt.text(float(dict_sizing[i][0]), float(dict_sizing[i][1]),
             str(list(reqeusted_dict.keys())[i]),
             size = dict_sizing[i][2], rotation=dict_sizing[i][3],
             ha="center", va="center",
             bbox=dict(boxstyle="round4",
                   ec=(0, 0, 0),
                   fc=(1, 1, 1),
                   )
         )
    
plt.axis('off')
plt.show()

plt.save('file location')
