# 이진법(binary)
다 아시겠지만,,  저는 몰라서 공부해왔습니다

<br><br>


## 이진법이란 ? 
0과 1로만 표현한 수  

![alt text](image-5.png)

```python
0000 0000  # 0  
0000 0001  # 1
0000 0010  # 2
0000 0011  # 3
```
<br><br>

## 프로그래밍에서 왜 2진법을 알아야 하는가 ? 

오류의 최소화와 효율성(비용, 시간) 때문
<br><br>


## 이진법 연산자

비트연산자 소개
![alt text](image-2.png)

>📌 참고  
1 << k 는 1(2**0)을 k번 미는것과 같음  
1 << 0 은 0001  1(10)  
1 << 1 은 0010  2(10)  
1 << 2 는 0100  4(10)  
1 << 3 은 1000  8(10)
즉, 1 << k는 2 ** k와 같음

<br><br>

## 비트연산 활용

* 홀짝 비교
* 2의 제곱수인지 확인하기
* 2진수에서 1의 개수 찾기
* 비트마스킹 개념 이용한 알고리즘 풀이 (비트를 이용하여 집합을 표현, 처리)
    - [다빈치코딩알고리즘](https://wikidocs.net/206598)
* 실무에서는 임베디드, 통신 프로토콜, 암호화 등에 자주 사용 (빠르기때문에 성능이 중요한 시스템에 자주 사용)

<br><br>

## 문제 선택 이유
기업의 코테는 어떤 수준인지 궁금했고 , 비트연산자 개념 적용이 어려워서 찾아봤습니다

<br><br>

## 이번 문제에서 제가 사용한 함수, 연산자
* bin(num)
![alt text](image-1.png)

    - bin(num)[2:]

* .zfill(num)  
Python String zfill() Method
![alt text](image-6.png)
![alt text](image-7.png)
![alt text](image-4.png)

* | 연산자 (or 연산자)


<br><br>

## 문제 접근 방법 

1. 비트연산이 필요하다 -> or 연산자가 필요(|)
2. 비트연산 값을 이진법으로 변환
3. n의 길이만큼 0으로 채우기
4. 이진법에서 1을 #으로, 0을 공백으로 대체
<br><br>



## 내 코드 

```python
def solution(n, arr1, arr2):
    answer = []
    for i in range(n) :
        answer.append((bin(arr1[i] | arr2[i])[2:].zfill(n)).replace('1', '#').replace('0', ' '))
    return answer
```