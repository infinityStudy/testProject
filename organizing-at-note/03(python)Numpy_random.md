
## **Numpy의 random 함수**
> <span style="color:blue">import numpy</span> 으로 임포트한다.

### **random값의 특징**
* 랜덤 값은 기본적으로 0과 1사이의 값을 추출한다.(**0 $\leq$x < 1**)

  ### **random 주요 함수**

> form numpy import random as nprn 로 import한 경우

함수명 | 설명 | 사용법
:-:|:--|:--
.random()|o 0과 1사이의 임의 숫자를 지정한 만큼 생성한다. | o nprn.randmom((2,2)) : 2x2행렬<br> o nprn.random(2) 숫자 3개를 벡터 리스트로 생성
.rand() |o 지정한 숫자 만큼 임의의 값 배열을 생성한다. | o nprn.rand(3,2) : 3x2 행렬생성<br> o nprn.rand(10)
.randint()|o 지정한 하한,상한 사이의 임의 값을 정수로 추출|o nprn.randint(5) : 5미만의 정수 1개 추출<br>o nprn.randint(10,size=4) : 10미만의 정수 4개 추출<br>o nprn.randint(20,25,size=3) : 20에서 25사이의 정수 3개 추출<br>o nprn.randint(10,20,size(2,2)) : 10에서 20사이의 정수를 추출하고 2x2 행렬만듦
.randn() |o 표준편차가 1이고, 평균값이 0인 표준정규분포 상에서의 랜덤 값을 추출한다. | o nprn.random(2,3) : 2x3행렬로 생성<br>o nprn.randn(5) : 5개의 값을 추출
.normal() |o 평균과 표준편차를 지정한 정규분포 상에서의 랜덤 값을 추출한다. | o nprn.normal(평균,표준편차, 추출갯수)<br>o nprn.normal(0,0.01,10) : 평균 0, 표준편차 0.01인 값 중 10개 추출
.uniform() |o 지정한 하한값을 포함하고, 상한값 미만의 수를 size만큼 추출한다. | o nprn.uniform(5) : 5미민의 난수 1개 추출<br>o nprn.uniform(5,7) : 5와 7사이의 난수 1개 추출<br>o nprn.uniform(5,7,10) : 5와 7사이의 난수 10개추출, size=10과 동일 <br>o nprn.uniform(5,7,size=(4,2)) : 4x2의 행렬로 추출
.choice() | o 지정한 숫자 미만의 갯수만큼 정수를 선택 추출하는데, 확률과 중복추출여부로 선택하여 추출한다.|o nprn.choice(5) : 5미만의 정수에서 1개 선택 추출 <br>o nprn.choice(5,3,replace=True/False) : 중복 선택여부 지정하여 추출 <br> o nprn.choice(5,3,repalce=False, p=[0.3,0.2,0.1,0.0,0.9]) : 5미만의 정수를 3개 추출하는데, 중복추출은 안되고, 확률로 1은 0.3, 2는 0.2..의 확률로 추출한다.
.permutation() | 지정한 숫자 미만의 수를 랜덤하게 순서를 섞어서 추출한다. | o nprn.permutation(5) : 5미만의 수를 추출하는데 랜덤하게 섞어서 추출한다.
.shuffle(data) | 지정한 data를 랜덤하게 섞어준다| x = ['가','나','다',3,4,5]<br> nprn.shuffle(x)<br> print(x)


```python
import numpy

print(numpy.random.random(5))
print('##################################')
print(numpy.random.random((3,4)))
```

    [0.45626775 0.13593018 0.30941056 0.15017301 0.90217232]
    ##################################
    [[0.4752434  0.67826617 0.96418185 0.61328947]
     [0.00508402 0.42149647 0.96561559 0.63961054]
     [0.65826739 0.90463923 0.80670366 0.14628384]]
    


```python
print(numpy.random.randn(5))
print('##################################')
print(numpy.random.randn(3,4))
```

    [-0.70373465  0.86712104  0.64247852  0.12092068  0.20700976]
    ##################################
    [[ 0.12568537 -0.42938627  0.74699779  0.50445166 -1.50258931]
     [-1.1978323  -0.39397974  0.50855532 -0.99309269  0.54845169]]
    


```python
print(numpy.random.rand(5))
print('##################################')
print(numpy.random.rand(3,4))
```

    [0.42441305 0.70418925 0.98605908 0.26258795 0.61000537]
    ##################################
    [[0.90082264 0.72817514 0.71961584 0.69482523]
     [0.40073351 0.62677296 0.5698146  0.98850221]
     [0.33132573 0.70423379 0.4182938  0.79029234]]
    


```python
print(numpy.random.uniform(5))
print()
print(numpy.random.uniform(5,7))
print()
print(numpy.random.uniform(5,7,5))
print(numpy.random.uniform(5,7,size=5))
print()
print(numpy.random.uniform(5,7,(3,2)))
print(numpy.random.uniform(5,7,size=(3,2)))
print()
```

    1.3545415658546118
    
    5.503388054957927
    
    [6.0549053  5.91181809 6.46891932 6.15469729 5.06109921]
    [5.62797225 6.97910288 5.20252159 5.59411922 6.89446515]
    
    [[5.28863228 6.41639029]
     [5.52315307 6.04840072]
     [5.13852336 5.31487927]]
    [[5.39620547 6.50754765]
     [5.43299998 5.3340781 ]
     [6.45018127 5.87451232]]
    
    


```python
print(numpy.random.randint(5,20,size=(3,3)))
print()
```

    [[16  5  6]
     [13  7  6]
     [ 8  5  5]]
    
    


```python
x = numpy.random.randint(1,10,size=7)
x = ['가','나','다',3,4,5]
print(type(x))
print(x)
numpy.random.shuffle(x)
print(x)
print(type(x))
```

    <class 'list'>
    ['가', '나', '다', 3, 4, 5]
    ['나', 3, '가', '다', 5, 4]
    <class 'list'>
    
