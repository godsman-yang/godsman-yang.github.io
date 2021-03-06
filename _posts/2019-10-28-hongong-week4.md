---
layout: post
title: '혼자 공부하는 파이썬 - 4주차 미션'
date: 2019-10-28 08:00
categories: [language, python]
# os, windows, linux, 
# service, github
# language, python, c
# etc, blog, jekyll
---

# 4 주차
223쪽 [직접 해보는 손코딩: 범위 내부의 정수를 모두 더하는 함수] 실행 후 코드가 입력된 화면 및 실행결과 화면 인증샷

매개변수, 기본 매개변수, 가변 매개변수에 대해 간략하게 정리한 내용 포스팅하기

## 기본 미션
223쪽 [직접 해보는 손코딩: 범위 내부의 정수를 모두 더하는 함수] 실행 후 코드가 입력된 화면 및 실행결과 화면 인증샷

입력된 화면
```python
# 함수를 선언합니다.
def sum_all(start, end):
    # 변수를 선언합니다.
    output = 0
    # 반복문을 돌려 숫자를 더합니다.
    for i in range(start, end + 1):
        output += i
    #리턴합니다.
    return output

# 함수를 호출합니다.
print("0 to 100:", sum_all(0, 100))
print("0 to 1000:", sum_all(0, 1000))
print("50 to 100:", sum_all(50, 100))
print("500 to 1000:", sum_all(500, 1000))
```

실행결과
```bash
/Users/shyang/work/hongong-python/sum_all_basic.py
0 to 100: 5050
0 to 1000: 500500
50 to 100: 3825
500 to 1000: 375750
```

## 선택미션
매개변수, 기본 매개변수, 가변 매개변수에 대해 간략하게 정리한 내용 포스팅하기

### 관련 용어
- 함수 -
- 매개변수 - 함수를 호출할 때 함수로 넘겨주는 자료
- 리턴값 - 함수가 실행하고 돌려주는 결과값

#### 매개변수
함수를 호출할 때 함수로 넘겨주는 자료
- 정의한 개수보다 적게 넘겨 주면 - TypeError
- 정의한 개수보다 많이 넘겨 주면 - TypeError
- def function(일반매개변수A, 일반매개변수B, *가변매개변수, 기본매개변수A=10, 기본매개변수B=20):

#### 기본 매개변수
- 매개 변수를 입력하지 않았을 때 기본적인 값을 지정하는 매개 변수
- 기본 매개 변수는 가장 마지막에 입력을 한다
- 가변 매개 변수와 기본 매개변수를 함께 사용하면 모든 매개 변수는 가변 매개변수로 전달되고 기본 매개변수로 값이 전달되지 않는다

#### 가변 매개변수
매개변수를 함수에 정의한 것과 같지 않은 개수를 넘겨주면 TypeError 가 발생

print 함수처럼 매개 변수의 개수가 다양할 수 있다. 가변 매개 변수라고 한다.
- 가변 매개변수는 매개변수 앞에 별표를 붙인다 - *가변매개변수
- 가변 매개변수는 한 함수에서 하나만 사용할 수 있다
- 가변 매개변수는 매개 변수의 마지막에 적는다. 기본 매개변수보다는 앞에.

#### 키워드 매개변수
print() 함수 참고
- 가변 매개변수와 기본 매개변수를 사용할 경우에 변수의 이름과 값을 전달하면 된다.
- 키워드 매개변수는 위치와 관계없이 입력 가능하다

## 혼자 공부하는 프로그래밍 - 파이썬
혼자 공부하는 프로그래밍 [파이썬-소개](https://godsman-yang.github.io/hongong-python)와 미션을 정리했습니다.
* [1주차 미션](https://godsman-yang.github.io/hongong-week1) 
* [2주차 미션](https://godsman-yang.github.io/hongong-week2) 
* [3주차 미션](https://godsman-yang.github.io/hongong-week3) 
* [4주차 미션](https://godsman-yang.github.io/hongong-week4) 
* [5주차 미션](https://godsman-yang.github.io/hongong-week5) 
* [6주차 미션](https://godsman-yang.github.io/hongong-week6) 

## 미션 외 자료 정리
[혼공 노트](https://godsman-yang.github.io/hongong-note)
