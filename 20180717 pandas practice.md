#### 20180717 TIL

 ## pandas로 국민청원 데이터 분석

*  seaborn / matplotlib 의 튜토리얼 보고 그래프 그리기  

  -> 예제 따라해보기  

```
df2 = pd.DataFrame({'A' : 1.,  #숫자 뒤에 . : float형으로 출력됨
                    'B' : pd.Timestamp('20130102'),  # Timestamp:날짜 형식으로
                    'C' : pd.Series(1,index=list(range(4)),dtype='float32'),
                    'D' : np.array([3] * 4,dtype='int32'),
                    'E' : pd.Categorical(["test","train","test","train"]),
                    'F' : 'foo' })
```

```
df2.describe?  # 도움말 나옴
```

```
df2.A                  df2.bool
df2.abs                df2.boxplot
df2.add                df2.C
df2.add_prefix         df2.clip
df2.add_suffix         df2.clip_lower
df2.align              df2.clip_upper
df2.all                df2.columns
df2.any                df2.combine
df2.append             df2.combine_first
df2.apply              df2.compound
df2.applymap           df2.consolidate
df2.D
```

-> 윗부분과 마지막 부분을 확인할 수 있음  

axis=1  ->축 별로 정렬  

axis=0 ->값 별로  

```
df['A']
df[['A','B']]  # 여러 칼럼 뽑아오고 싶을 때: 괄호 하나 더 넣어주면 됨!
```

```
df[:]  # 모든 인덱스 가져오기
```

```  
df['20130102':'20130104']  # 날짜는 인덱스로 지정해줘야 가져올 수 있음. 중복값이 없는 고유값일 때만 인덱스로 지정 가능
```

파이썬 길들이기 실습  

파이썬 2에서 3 바뀐 부분 바꾸면서 하기  

colab에서 파이썬 버전 바꾸기 - 런타임-런타임 유형 변경  

  

conda install -c conda-forge jupyterlab  

https://www.python.org/dev/peps/pep-0008/ - python style guide  

  

주피터 노트북 - 가장 아래 코드만 출력됨!!  

object 형태 데이터 : string(문자)  

줄 바꿀 부분에 \ 하면 줄바꿔도 한줄로 인식  

```
never_marriage\

.sort_index(axis=1)
```



loc - location의 약자