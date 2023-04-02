# EDA

## EDA 기본

### directory list

```python
from glob import glob

base_dir = "C:/Users/smisl/Documents/project/GitHub/2023-1-OC-AI-Study/Week3/03_EDA_실습데이터/"
file_lst = glob(base_dir + "*.csv")
```

### 특정한 데이터만 조회

* contains

    ```python
    concat_df = concat_df[concat_df["도로명주소"].str.contains("마포구")]
    ```

* startswith

    ```python
    concat_df = concat_df[concat_df["상호명"].str.startswith("스타벅스")]
    ```

### font

```python
from matplotlib import font_manager, rc

font_path = "C:/Windows/Fonts/NGULIM.TTF"
font = font_manager.FontProperties(fname = font_path).get_name()

rc("font", family = font)
```

## 마케팅 데이터 EDA

### read data

```python
df = pd.read_csv("C:/Users/smisl/Documents/project/GitHub/2023-1-OC-AI-Study/Week3/archive/Train.csv")
```

### 결측치 확인

* isnull()

    ```python
    import missingno as msno

    df.isnull().sum(axis = 0)
    ```

* matrix

    ```python
    msno.matrix(df)
    ```

* bar

    ```python
    msno.bar(df)
    ```

### correlation check

```python
import numpy as np

mask = np.zeros_like(df.corr())
mask[np.triu_indices_from(mask)] = True

sns.heatmap(df.corr(), annot = True, fmt = ".2f", mask = mask)
```

* annot = True
    
    박스 안에 데이터 표시

* fmt = ".2f"

    박스 안에 표시되는 데이터의 서식 지정

* mask

    heatmap의 절반만 표시