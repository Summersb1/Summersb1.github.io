---
title: Command Lists
published: 2024-11-13
description: ''
image: ''
tags: [모딩]
category: '3Dmigoto'
draft: false 
---

|섹션|역할|
|---}---|


섹션 : ShaderOverride, ShaderRegex, TextureOverride, CustomShader, BuiltInCustomShader, BuiltInCommandList, Present, ClearRenderTargetView, ClearDepthStencilView, ClearUnorderedAccessViewUint, ClearUnorderedAccessViewFloat, Constants, Profile, ShaderRegex

---

### 기본 자료형과 변수 선언

이 언어에서는 **변수를 선언하고 초기화**하는 몇 가지 방법이 있으며, 각각의 변수가 **특정 네임스페이스에 속하도록 설정**됩니다. 이를 통해 다른 파일에 포함된 변수들과 이름 충돌 없이 독립적으로 사용할 수 있어요. 

변수에는 **실수(float) 값**이 할당될 수 있으며, 모든 전역 변수는 `[Constants]`라는 특정 영역에 선언됩니다.

### 변수 선언 방식

1. `global $변수명`  
   변수를 선언할 때 별도로 초기값을 지정하지 않으면, 자동으로 **0.0**으로 초기화됩니다.

   ```ini
   global $myVariable
   ```

2. `global $변수명 = 초기값`  
   변수를 선언할 때 **초기값을 함께 지정**할 수 있습니다.

   ```ini
   global $myVariable = 5.5
   ```

### 지속 변수 (Persist Variable)

변수 앞에 `persist` 키워드를 추가하면, 이 변수는 프로그램이 종료되거나 **설정을 다시 불러올 때(F10)** 자동으로 `d3dx_user.ini` 파일에 **저장**됩니다. 

   ```ini
   global persist $myPersistentVariable = 1111
   ```

## 지역 변수 (Local Variable)

> `persist` 변수를 사용하면, 다음에 프로그램을 실행할 때 `d3dx_user.ini`에 저장된 값을 자동으로 불러와 사용해요. 단, `Ctrl+Alt+F10`을 눌러 `d3dx_user.ini` 파일을 초기화하면, 저장된 값도 초기화됩니다.

### 요약

- 전역 변수는 `[Constants]`에서 선언하고, 네임스페이스를 통해 이름 충돌을 방지합니다.
- `persist` 키워드를 사용하면, 프로그램 종료 후에도 변수가 유지됩니다.



## 대입

1. 사용자 선언 변수에 대입
2. IniParams에 대입

## 특별한 피연산자 키워드



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