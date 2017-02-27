---
title: "디버거 컨텍스트 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [디버깅 SDK] 컨텍스트"
ms.assetid: 79808036-b680-4e4c-9c61-4ed43aa11323
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# 디버거 컨텍스트
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버깅을 디버그 엔진 \(DE\) 동시에 여러 가지 컨텍스트 내에서 다음과 같이 작동 합니다.  
  
-   프로그램의 실행 스트림 내의 현재 위치를 설명 하는 코드 컨텍스트.  
  
-   문서 컨텍스트 또는 원본 문서 내의 현재 위치를 설명 하는 위치입니다.  
  
-   어떤 식의 계산 수행할 컨텍스트를 설명 하는 식 평가 컨텍스트.  
  
## 단원 내용  
 [코드 컨텍스트](../../extensibility/debugger/code-context.md)  
 프로그램의 명령 스트림에 위치 코드 지침, 하지만 몇 가지 다른 방법을 사용 하 여 나타낼 수 있습니다지 않습니다 않던 언어와 오늘날의 런타임 아키텍처에서 주소로 코드 컨텍스트를 설명 합니다.  
  
 [문서 위치](../../extensibility/debugger/document-position.md)  
 Visual Studio IDE로 알려진 소스 파일의 위치를 추상화 디버깅에 문서 위치를 정의 합니다.  
  
 [문서 컨텍스트](../../extensibility/debugger/document-context.md)  
 설명 Visual Studio 소스 파일에는 디버깅에 어떤 문서 컨텍스트를 나타냅니다.  또한 기호 처리기 설명서 컨텍스트로 코드 컨텍스트를 매핑하는 방법에 대해 설명 합니다.  
  
 [식 평가 컨텍스트](../../extensibility/debugger/expression-evaluation-context.md)  
 Visual Studio 식 평가 컨텍스트에 정보를 제공합니다.  예를 들어, 스택 프레임과 연결 된 식 평가 컨텍스트 로컬 변수, 메서드 매개 변수 및 클래스 멤버를 확인 하기 위해 컨텍스트를 제공 합니다.  
  
## 관련 단원  
 [디버깅 개념](../../extensibility/debugger/debugger-concepts.md)  
 디버깅의 주요 아키텍처 개념에 설명 합니다.  
  
 [디버깅 구성 요소](../../extensibility/debugger/debugger-components.md)  
 디버그 엔진 \(DE\), 식 계산기 \(EE\) 기호 처리기 \(SH\) 등 Visual Studio 디버깅 구성의 개요를 제공 합니다.  
  
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)  
 프로그램을 시작 하 고 식을 계산 하는 것과 같은 다양 한 디버깅 작업에 대 한 링크가 포함 되어 있습니다.