---
title: "디버거 확장성 시작 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "시작, 디버깅 SDK"
  - "디버깅 [디버깅 SDK]를 시작 하기"
  - "시작, 디버깅 SDK"
ms.assetid: d6ce6f43-1409-4bf7-93cd-f3464ca23504
caps.latest.revision: 17
caps.handback.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
---
# 디버거 확장성 시작
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 를 만들고 내에서 프로그램을 디버깅 하는 데 사용 되는 디버거 구성 요소를 사용자 지정 하는 데 필요한 정보를 제공의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 환경입니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]디버깅이 개선 사항 이전에 수행한 테스트는 다양 한 유용성에서 파생 된 추가 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버거.  사용할 수 있는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버깅 단계를 통해 다중 언어 응용 프로그램, 또는 사용자에 구현할 수 있습니다 응용 프로그램 및 다국어 솔루션을 디버깅 하는 동안 즉석에서 변수를 편집 합니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]디버깅 실행된 아웃 프로세스 디버깅 중인 프로그램 이므로 응용 프로그램의 프로세스 공간에서 덜 침입적 인입니다.  따라서 디버깅 프로그램을 영향을 주지 않고 디버거를 상호 작용 하는 구성 요소를 작성 하는 것이 더 쉽습니다.  
  
 가장 잘 사용 하는 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], 잘 알고 있어야 합니다.  
  
-   [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\)  
  
-   C \+ \+ 프로그래밍 언어  
  
-   ATL COM  
  
## 단원 내용  
 [디버거를 확장 하기 위한 로드맵](../../extensibility/debugger/roadmap-for-extending-the-debugger.md)  
 디버깅 컴파일러 출력에 따라 해당 제품에서을 구현 하는 과정에 간략하게 설명 합니다.  
  
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)  
 개요는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버그 엔진 \(DE\), 식 계산기 \(EE\) 및 기호 처리기 \(SH\)를 포함 하는 구성 요소를 디버깅 합니다.  
  
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)  
 디버깅의 주요 아키텍처 개념에 설명 합니다.  
  
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)  
 디버그 엔진 \(DE\) 동시에 코드, 설명서, 및 식 평가 컨텍스트 내에서 작동 하는 방식을 설명 합니다.  각각의 세 가지 컨텍스트, 위치, 위치 또는 평가 관련 된으로 설명합니다.  
  
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)  
 프로그램을 시작 하 고 식을 계산 하는 것과 같은 다양 한 디버깅 작업에 대 한 링크가 포함 되어 있습니다.