---
title: 3Dmigoto 소개
published: 2024-11-13
description: '게임 모딩에 주로 사용되는 3Dmigoto 프로그램에 대한 소개'
image: ''
tags: [모딩]
category: '3Dmigoto'
draft: false 
---

:::warning
**면책조항**

본 글은 교육적인 목적을 위해 작성된 자료입니다. 이 자료에서 제공하는 모든 정보는 학습 및 연구 목적으로만 사용되며, 해당 내용으로 인한 법적 문제나 책임은 사용자에게 있습니다. 이 글은 게임 모딩의 일반적인 이해를 돕기 위한 것이며, 이를 실제 게임에 적용하는 데 있어 발생할 수 있는 문제에 대해서는 책임을 지지 않습니다.
:::

## 3Dmigoto?

3Dmigoto란 3D 게임에서 입체적 시각 효과를 수정하기 위한 DX11 Wrapper.

::github{repo="bo3b/3Dmigoto"}

이 도구는 셰이더 코드 수정, 그래픽 버그 수정, 텍스처 수정 등의 기능을 제공함.

셰이더 분석 및 디버깅 도구(프레임 덤프, 헌팅 모드)를 통합하고 있음.

### Wrapper?

Wrapper는 다른 프로그램이나 라이브러리를 감싸서 인터페이스를 제공하거나 기능을 확장하는 소프트웨어 구조.

주로, 기존의 시스템에 추가적인 기능을 제공하거나, 복잡한 작업을 단순화하기 위해 사용됨.

예를 들어, DX11 wrapper는 DirectX 11 API에 기능을 추가하거나 수정하여 개발자가 특정 작업을 더 쉽게 할 수 있도록 도와주는 역할.

## 작동원리

3Dmigoto의 핵심 기능은 게임의 렌더링 파이프라인을 가로채어 특정 셰이더의 동작을 수정하는 것.

게임이 그래픽 관련 명령들 GPU에 보내기 위해 API를 호출할 때 그걸 가로채 원하는 작업을 수행할 수 있도록 함.

3Dmigoto는 **DLL 인젝션(DLL Injection)** 을 사용함.

DLL 인젝션은 실행 중인 게임 프로세스에 동적 링크 라이브러리(DLL)를 삽입하여, 게임의 동작을 수정하거나 개입할 수 있게 하는 기술임.

3Dmigoto는 이 기술을 이용해 게임의 DirectX 호출을 가로채고, 이를 수정하여 실시간으로 셰이더를 수정하거나 그래픽 관련 문제를 해결할 수 있음.

DLL 인젝션을 통해 3Dmigoto는 게임의 렌더링 파이프라인에 영향을 미치며, 사용자가 시각적 효과를 수정하거나 그래픽 버그를 해결할 수 있게 됨.

이 과정에서 3Dmigoto는 게임과 GPU 사이에서 중간자 역할을 하며, 게임이 실행되는 동안 실시간으로 수정 작업을 할 수 있음.

## 3Dmigoto 디렉터리 및 파일

* `Mods/*` : 여기에 모드 파일들이 들어감
* `ShaderCache/*` : 캐시된 셰이더 파일이 여기에 저장됨
* `ShaderFixes/*` : 특정 셰이더를 교체할 때 사용됨
* `3DMigotoLoader.exe`(실행파일 이름은 다를 수 있음) : 3Dmigoto 실행파일
* `d3dx.ini` : 3Dmigoto의 전역적인 설정 파일
* `d3dx_user.ini` : persist 변수 값 저장 파일

## 게임 모딩에서의 3Dmigoto 역할

최근 3Dmigoto는 게임의 시각적 요소를 개선(사용자 정의 모델, 셰이더 수정, 투명화 우회, UI 수정, 등등)하는데 사용되어지고 있음

## 파생된 도구들

게임 모딩을 위해 3Dmigoto를 사용하는 프로그램은 다음과 같음

각 프로그램들은 특정 게임에 호환되도록 수정된 3Dmigoto 버전임

* GIMI : GI-Model-Importer(원신)

::github{repo="SilentNightSound/GI-Model-Importer"}

* ZZMI : Zenless-Zone-Model-Importer(젠레스 존 제로)

::github{repo="leotorrez/ZZ-Model-Importer"}

* SRMI : Star-Rail-Model-Importer(붕괴: 스타레일)

::github{repo="SilentNightSound/SR-Model-Importer"}

* XXMI : XXMI Launcher

원신, 젠레스 존 제로, 붕괴 스타레일, 명조 통합 런쳐

자동 업데이트 지원, 비프음 제거 기능

::github{repo="SpectrumQT/XXMI-Launcher"}

## 게임 모딩 자료 및 정보 공유 사이트

* **Gamebanana** : https://gamebanana.com/
* **미호요스킨모드 채널(아카라이브)** : https://arca.live/b/genshinskinmode
* **Caimogu** : https://www.caimogu.cc/
* **AGMG(디스코드 채널)** : https://discord.com/invite/agmg
