# Pandas

>Numpy가 같은 타입의 배열만 처리할 수 있는데 반해, 데이터 타입이 다양하게 섞여있을 때도 처리가능
>
>Pandas는 Series(시리즈), DataFrame(데이터프레임), Panel(패널) 세가지의 데이터 구조 사용 (데이터프레임 가장 多)



#### 구조적 데이터 생성하기

- Series로 데이터 생성

  ```python
  import pandas as pd
  s = pd.Series(data)
  ```

  - 시리즈는 1차원 배열의 값에 각 값에 대응되는 인덱스를 부여할 수 있는 구조

    - 출력 시 인덱스 함께 표시

  - data에는 시퀀스데이터(seq_data)와 딕셔너리 데이터(dict_data)

    - 시퀀스데이터(seq_data)로는 리스트와 튜플 (주로 리스트 사용),

  - s1.index : 인덱스만 출력

  - s1.values : 값만 출력

  - np.nan은 특정원소가 없음을 표시함

    ```
    s = pd.Series([np.nan,10,30])
    >> 0 NaN
       1 10
       2 30
    
    ```

  

- 날짜 자동생성 : date_range

  ```python
  pd.date_range(start='2020-01-19',end='2020-01-28')
  ```

  - 시작 날짜부터 끝 날짜까지 하루씩 증가한 리스트 생성 (끝 날짜도 포함)

  - 입력형식은 yyyy-mm-nn, yyyy/mm/nn, yyyy.mm.dd (yyyy,mm,dd 순서 바꿔도 됨) 등 다양하게 가능하지만 출력형식은 yyyy-mm-dd임

  - 끝 날짜 지정대신 periods로 기간을 정해줘도 됨

  - freq함수로 옵션지정 가능

    - pandas date_range() 함수의 freq 옵션

      ![image](https://user-images.githubusercontent.com/58683097/72668489-d1dbaa80-3a6a-11ea-826d-23e0d0960bad.png)

    - [참고사이트][https://pandas.pydata.org/pandas-docs/stable/user_guide/timeseries.html]



- DataFrame으로 데이터 생성

  ```python
  df = pd.DataFrame(data [,index=index_data, columns=columns_data])
  ```

  - 리스트 형태와 유사한 데이터 타입은 모두 사용가능
    - 리스트, 딕셔너리, ndarray, Series, DataFrame 등
    - 세로축 index, 가로축 columns, 나머지 values



#### 데이터 연산

- Series, DataFrame 끼리 연산가능 (사이즈 달라도 ok, 계산안되는 부분은 NaN)
- df.describe() : 평균, 표준편차, 최솟값, 최댓값 등 한번에 구할 수 있음 (R의 Summary랑 비슷)



#### 데이터를 원하는 대로 선택하기

- df.head() : R에서 head랑 같음. but 열이름포함해서 6행. 즉, 값은 5행만 나옴
- df.tail() : R에서 tail과 같음

- df[행시작위치:끝위치] : 시작부터 끝까지 (끝번호 포함 X)
- df.loc[index_name] : index이름 지정했으면 그걸로도 선택가능
- df.loc[column_name] : columns이름으로도 선택가능
- df[column_name] [start_index_name:end_index_name] : 열 지정 후 행 범위 선택가능(index_name도 가능하고 index 위치도 가능)
- df.T : 전치행렬만듦
- df[[열이름1,열이름3,열이름4,열이름2]] : 열 순서 맘대로 가능



#### 데이터 통합하기

- df1.append(df2 [,ignore_index=True]) : 행 붙이는 거
  - ignore_index=True 데이터 순서대로 새로운 index할당
  - ignore_index=True안쓰면 기존 데이터의 index유지
- df1.join(df2) : 열 붙이는 거
  - 행길이 안맞아도 ok, NaN표시됨
- df_left.merge(df_right, how=merge_method, on=key_label) : 특정 열기준으로 붙이는 거
  - how 선택인자
    - left : 왼쪽데이터 모두 + 지정된 열(key 값)이 있는 오른쪽 데이터선택
    - right : 오른쪽        〃       +               〃                 왼쪽 데이터 선택
    - outer : 지정된 열 기준으로 왼쪽,오른쪽 모두 선택
    - inner : 지정된 열 기준으로 공통항목만 선택 (default)



#### 데이터 파일 읽고 쓰기

- pd.read_csv(file_name [,options]) : 표 형식 읽기

  - options
    - encoding = "utf-8" : utf-8로 인코딩
    - sep = " " : 구분자가 공백
    - index_col = "열이름" : 특정 열을 인덱스로 지정

- DataFrame_data.to_csv(file_name [,options]) : 표 형식 쓰기

  

[실습][https://github.com/uzchu/Python-in-multi/blob/master/notebook/Chapter_11_NumPy_pandas.ipynb]