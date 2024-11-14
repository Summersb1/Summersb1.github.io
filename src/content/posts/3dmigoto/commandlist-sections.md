---
title: INI 섹션 설명
published: 2024-11-13
description: ''
image: ''
tags: [모딩]
category: '3Dmigoto'
draft: false 
---

CommandList는 일종의 함수처럼 사용되는 섹션으로, 이 안에서는 `if-elif-else` 같은 조건문과 `handling = skip`, `draw = from_caller` 같은 명령어들을 사용할 수 있습니다.

**TextureOverride**와 **ShaderOverride** 섹션은 CommandList의 파생 클래스와 비슷한 개념입니다. CommandList와 동일하게 조건문, 제어문, `draw`, `handling` 명령을 사용할 수 있으며, 추가적으로 특정 해시 값에 따른 조건부 실행 기능을 제공합니다.

- **TextureOverride**는 특정 텍스처의 해시 값을 입력받아, 현재 화면에 존재하는 텍스처의 해시와 매칭되면 섹션 내의 명령을 실행하는 방식입니다.
- **ShaderOverride**도 같은 원리로 작동하며, 지정된 셰이더 해시가 매칭되면 섹션 내의 명령이 실행됩니다.

여기서 "매칭"이란, 화면에 표시되는 텍스처나 셰이더의 고유 해시 값이 3DMigoto에서 제공된 TextureOverride나 ShaderOverride의 해시와 동일할 때 이를 일치된 것으로 간주해, 해당 명령이 실행되는 개념입니다.

이와 같이 CommandList는 기본 명령 집합을, TextureOverride와 ShaderOverride는 해시 값에 따른 조건부 실행 기능을 제공하여 더 다양한 명령 제어를 가능하게 합니다.

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

각 프레임의 시작/끝에 현재 호출에서 실행할 명령어

각 프레임이 시작될 때 커스텀 리소스 또는 ini 매개변수를 지우거나 커스텀 셰이더를 실행하여 원하는 작업을 수행하는 데 유용합니다. 

“post” 키워드는 프레임 끝이 아닌 프레임 시작 시 동작을 실행하게 하는데, 일반적으로 프레임이 끝날 때 오버레이가 그려지고 새 프레임이 시작될 때 리소스가 지워지기를 원합니다.

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
