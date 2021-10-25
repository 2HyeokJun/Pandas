# Pandas 매드무비

---------

1. ```['col3']```의 값이 30보다 작을 경우, df의 ```['col2'], ['col3']```을 nan으로 바꾸는 함수

```python
df.loc[df['col3']<30,['col2','col3']] = np.nan
```

2. ```glob``` 함수를 이용해 ```pickle```파일 합치기

```python
df = pd.concat(map(pd.read_pickle, glob.glob('data/pickle/after iqr/******.pkl')))
```

3. 특정 ```column```만 빼고 호출하고 싶을 때 :  ```index.difference```에 대한 [공식문서](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Index.difference.html) 

   ![image-20211006131246290](C:\Users\AskStory\AppData\Roaming\Typora\typora-user-images\image-20211006131246290.png)

```python
md = md[md.columns.difference(['elec', 'date', ...])]
```

4. ```columns```이름 바꾸기

   1. ```df = df.rename(columns = {'old1' : 'New1', 'old2' : 'New2', ...})```

   2. ```df.columns = ['New1', 'New2', 'New3', ...]```

      ​	1. ```df.columns```를 입력하면 모든 ```column```명이 나온다. 여기서 복붙해서 좀 더 쉽게 쓸 수도 있다.

5. 원하는 ```columns```만 마음대로 가져오기

   ```python
   df = ['realtime_start', 'value', 'date', 'realtime_end']에서 'date', 'value'만 이 순서로 가져오고 싶을때
   1. df = df.loc[:, ['date', 'value']]
   2. df = df[['date', 'value']]
   ```


6. ```DataFrame``` 회전

   ```python
   df = pd.DataFrame()일 때
   df_T = df.T
   ```


7. ```csv```파일 불러올때 ```column```명 설정하기

   ```python
   df = pd.read_csv('data.csv', names = column_array)
   ### 7-1. 다른 df의 column을 가져오고싶다면?
   column_array = df_column.columns.to_numpy()
   ```

   

