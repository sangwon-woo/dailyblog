---
toc: true
layout: post
description: Python Essential Reference Review
categories: [markdown, python, bookreview]
title: Technical Book Review - Python Essential Reference by David Beazley
---
# 파이썬 완벽 가이드
기술도서 리뷰에서는 각 챕터를 읽으면서 새롭게 알게된 내용 또는 기존에 잘못 알았던 내용, 개념에 대한 확실한 정의 등을 중심으로 기술한다.
## Chapter 01. 파이썬 맛보기
### 파이썬 실행하기
- 파이썬 프로그램은 인터프리터에 의해 실행

### 변수와 산술 표현식
``` python
# code1.1 간단한 복리 계산
principal = 1000
rate = 0.05
numyears = 5
year = 1
while year <- numyears:
    principal = principal * (1 + rate)
    print(year, principal)
    year += 1
```
> 포맷 문자열로 표현
`print('{:3d} {:0.2f}'.format(year, principal))`
"%d", "%s", "%f"는 각각 정수, 문자열, 부동소수점 데이터 타입의 포맷을 지정

### 조건문
- 복잡한 조건을 작성하다보면 줄이 길어질 수 있다. 이럴 때는 역슬래시를 넣어주면 된다.
- (), {}, []로 둘러싸인 코드에서는 역슬래시를 넣을 필요가 없다.

### 파일 입력과 출력
```python
# 다음은 파일을 열어 한 줄씩 내용을 읽는다.
f = open('foo.txt')
line = f.readline()
while line:
    print(line)
    line = f.readline()
f.close()
```
- 데이터 컬렉션(입력줄, 숫자, 문자열 등)에 대해 루프를 도는 것을 흔히 반복(iteration)이라고 한다. 
프로그램의 출력을 파일에 쓰려면 다음과 같이 하면 된다.
```python
f = open('out', 'w') # 쓰기용으로 파일을 연다.
while year <= numyears:
    principal *= (1 + rate)
    print("%3d %0.2f\n" % (year, principal), file = f)
```
위의 예들은 파일에 관한 것이지만, 동일 기법을 인터프리터의 표준 입력 스트림과 표준 출력 스트림에도 적용할 수 있다.
사용자 입력을 읽어 들이려면 `sys.stdin` 파일을 읽으면 되고, 화면에 데이터를 출력하고 싶으면 `sys.stdout`을 쓰면 된다.

### 문자열