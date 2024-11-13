---
title: CommandList 문법
published: 2024-11-13
description: ''
image: ''
tags: [모딩]
category: '3Dmigoto'
draft: false 
---

ini 파일의 각 섹션에서 사용할 수 있는 문법. (C++과 유사함.)

## 변수 선언 및 초기화

## 연산자

### 가장 높은 우선순위

* **!** : NOT (!rhs)
* **+** : 양수 (+rhs)
* **-** : 음수 (-rhs)

### 높은 우선순위

* **\*\*** : 제곱 (pow(lhs, rhs))

* **\*** : 곱하기 (lhs * rhs)
* **/** : 나누기 (lhs / rhs)
* **//** : 몫 (floor(lhs / rhs))
* **%** : 나머지 (fmod(lhs, rhs))

* **+** : 더하기 (lhs + rhs)
* **-** : 빼기 (lhs - rhs)

* **<** : less then (lhs < rhs)
* **<=** : less then or equal (lhs <= rhs)
* **>** : greater then (lhs > rhs)
* **>=** : greater then or equal (lhs >= rhs)

### 낮은 우선순위

삼중 등호 연산자는 이진 동등성을 테스트함.

특히, 텍스처 필터링에서 주어진 슬롯에 아무것도 바인딩되지 않았음을 나타내기 위해 사용되는 음수 0을 테스트할 수 있음.

(일반 등호 연산자로는 음수 0을 테스트할 수 없는데, -0.0 == +0.0이기 때문임.)

* **==** :
* **!=** :
* **===** :
* **!==** :
* **&&** :
* **||** :

## 참과 거짓

* `1, true, yes, on` : 참 값을 가짐
* `0, false, no, off` : 거짓 값을 가짐

## 조건문

### if 문

### if / else 문

### if / elif / else 문



## 이동문

### run = CustomShader

### run = CommandList

## 제어문

### handling = skip

### handling = abort

## local 키워드

## pre, post 키워드

## 리소스 복사