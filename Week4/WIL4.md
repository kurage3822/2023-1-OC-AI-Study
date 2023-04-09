# EDA 필사

## EDA 소개

### factorplot vs catplot

* factorplot

    ```python
    sns.factorplot("Pclass", "Survived", hue = "Sex", data = data)
    ```

* catplot

    ```python
    sns.catplot(x = "Pclass", y = "Survived", hue = "Sex", kind = "point", data = data)
    ```

* 차이점

    0.9.0 버전 이상의 seaborn에서는 factorplot를 더이상 지원하지 않음

    대신 catplot를 지원하며 factorplot를 구현하기 위해서는 kinf = "point"를 추가해줘야 함

### violinplot

```python
sns.violinplot(x = "Pclass", y = "Age", hue = "Survived", data = data, split = True, ax = ax[0])
```

### extract

```python
data["Initial"] = data.Name.str.extract("([A-Za-z]+)\.")
```

### crosstab

```python
pd.crosstab(data.Initial, data.Sex).T 
```