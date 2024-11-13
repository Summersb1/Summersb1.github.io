---
title: INI 섹션 설명
published: 2024-11-13
description: ''
image: ''
tags: [모딩]
category: '3Dmigoto'
draft: false 
---

## [Constants] : 전역 변수 선언

전역 변수 선언은 `[Constants]` 섹션에서 이루어짐

이름이 지정된 변수들은 `네임스페이스`로 구분되므로 포함된 ini 파일이 자신만의 변수를 사용할 수 있으며, `이름 충돌`에 대해 걱정할 필요가 없음.

변수의 값으로는 `실수 형식의 값`을 입력받음.

### 방법

1. `global $변수명` : 초기화 없이 선언 (자동으로 `0.0` 으로 초기화)
2. `global $변수명 = 초기값` : 선언과 동시에 초기화

### persist 키워드

```ini
global persist $some_persistent_variable = 1111
```

변수명 앞에 `persist` 키워드를 추가하면, 종료 시 또는 F10(config_reload) 시 `d3dx_user.ini`에 자동으로 저장됨.

만약 `d3dx_user.ini`에 저장된 값이 있으면 위의 초기값 대신 `저장된 값`을 대신 사용함.

`Ctrl+Alt+F10(wipe_user_config)`을 사용하여 `d3dx_user.ini`를 삭제해 저장된 값을 삭제할 수 있음.

### [Constants] 섹션 예시

```ini

```

## namespace

ini 파일의 고유한 이름을 선언.

ini의 첫 줄에서만 선언 가능.

### 방법

```ini
namespace=고유한이름
```

## namespace 예시

```ini

```

## IniParams

```ini
x = 0.8
y = 1.0
z = 1.2
w = 2.0
y140 = 3
```

셰이더 내에서 접근할 수 있는 변수.

하지만 이 변수들은 네임스페이스가 없고 너무 많으면 다루기 어려울 수 있음.

## [Key] : 키 바인딩

https://learn.microsoft.com/ko-kr/windows/win32/inputdev/virtual-key-codes?redirectedfrom=MSDN


## [Present]

## [ShaderOverride]

## [ShaderRegex]

## [TextureOverride]

## [CustomShader]

## [CommandList]

## 잘 사용되지 않는 섹션

### BuiltInCustomShader

### BuiltInCommandList

### ClearRenderTargetView

### ClearDepthStencilView

### ClearUnorderedAccessViewUint

### ClearUnorderedAccessViewFloat
