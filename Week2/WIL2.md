# 시각화

## 시각화 기본

### line plot

```python
import matplotlib.pyplot as plt

x = [0, 1, 2, 3, 4, 5]
y = [123, 1, 59, 40, 10, 100]

plt.plot(x, y)
```

### title

```python
plt.title("Shape Like W")
```

### bar plot

```python
plt.bar(x, y)
```

### scatter plot

```python
import seaborn as sns

penguin_df = sns.load_dataset("penguins")

df = penguin_df.values

plt.scatter(df[:, 5], df[:, 2])
```

### subplots

```python
plt.subplot(1, 3, 1)
plt.plot(x, y)

plt.subplot(1, 3, 2)
plt.bar(x, y)

plt.subplot(1, 3, 3)
plt.scatter(x, y)
```

### figsize

```python
plt.figure(figsize = (12, 5))
```

### distribution

```python
sns.kdeplot(df[:, 5], fill = True, color = "orange")
```

### pie chart
```python
cars = ["AUDI", "BMW", "FORD", "TESLA", "JAGUAR"]
data = [23, 29, 41, 12, 17]

plt.pie(data, labels = cars, explode = (0, 0, 0.2, 0, 0), shadow = True, autopct = "%1.1f%%")
```

### box plot

```python
tips = sns.load_dataset("tips")

sns.boxplot(x = "size", y = "tip", data = tips)
```

## Decorating

### xlabel

```python
X = ["Tom", "Amy", "Jim", "Bill", "Pegi"]
Y = [8, 23, 52, 37, 64]

plt.bar(X, Y, color = "lightgray", edgecolor = "gray")
plt.xlabel("Salesperson", labelpad = 12, fontdict = {"size": 14, "weight": "bold", "color": "gray"})
```

### ylabel

```python
plt.ylabel("Revenue (1000 $)", labelpad = 12, fontdict = {"size": 14, "weight": "bold", "color": "gray"})
```

### colors

* plt.bar

    ```python
    plt.bar(X, Y, color = "lightgray", edgecolor = "gray")
    ```

* plt.xlabel | plt.ylabel

    ```python
    plt.xlabel("Salesperson", labelpad = 12, fontdict = {"size": 14, "weight": "bold", "color": "gray"})
    plt.ylabel("Revenue (1000 $)", labelpad = 12, fontdict = {"size": 14, "weight": "bold", "color": "gray"})
    ```

### text annotaion

```python
for rect in bar:
    height = rect.get_height()
    plt.annotate(height, xy = (rect.get_x() + (rect.get_width() / 2), height + 3), ha = "center", va = "top")
```

### 수직선과 수평선

```python
line_b = plt.axhline(45, color = "blue", linestyle = "dashed").zorder = 0
line_r = plt.axhline(15, color = "red", linestyle = "dashed").zorder = 0

plt.axhspan(0, 15, facecolor = "red", alpha = 0.2).zorder = 0
```

### ravel()

```python
import numpy as np

x = [[1, 2, 3],
     [4, 5, 6],
     [7, 8, 9]]

np.ravel(x)
```

### count plot

```python
titanic_df = sns.load_dataset("titanic")

sns.countplot(data = titanic_df, x = "alone", hue = "alive")
```