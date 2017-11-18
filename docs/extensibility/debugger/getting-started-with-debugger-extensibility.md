---
title: "디버거 확장성 시작 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- getting started, Debugging SDK
- debugging [Debugging SDK], getting started
- Debugging SDK, getting started
ms.assetid: d6ce6f43-1409-4bf7-93cd-f3464ca23504
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1419f4e45aefed59aa36b249568a53a47ad3c459
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="getting-started-with-debugger-extensibility"></a>디버거 확장성 시작
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 만들고 프로그램 내에서 디버그 하는 데 사용 되는 디버거 구성 요소를 사용자 지정 하는 데 필요한 정보를 제공는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 환경입니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]디버깅은 이전에 수행 하는 테스트가 광범위 한 유용성 향상 추가 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버거 합니다. 사용할 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 다국어 응용 프로그램을 통해 단계로 디버깅 즉석에서 응용 프로그램 및 다중 언어 솔루션을 디버깅 하는 동안 변수 편집 구현할 수 있습니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]디버깅은 실행된-out-of-process 디버깅 중인 프로그램 이므로 응용 프로그램의 프로세스 공간에 덜 개입 합니다. 결과적 디버깅 프로그램 영향을 주지 않고 디버거를 사용 하는 구성 요소를 작성 하는 것이 쉽습니다.  
  
 최대한의 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], 다음에 잘 알고 있어야 합니다.  
  
-   [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 (IDE)  
  
-   C + + 프로그래밍 언어  
  
-   ATL COM  
  
## <a name="in-this-section"></a>단원 내용  
 [디버거 확장 로드맵](../../extensibility/debugger/roadmap-for-extending-the-debugger.md)  
 컴파일러 및 출력에 따라 제품에서 디버깅을 구현 하는 과정에 간략하게 설명 합니다.  
  
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)  
 개요를 제공는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버그 엔진 (DE), 식 계산기 (EE) 및 기호 처리기 (SH)를 포함 하는 구성 요소를 디버깅 합니다.  
  
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)  
 기본 디버깅 아키텍처 개념을 설명합니다.  
  
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)  
 디버그 엔진 (DE) 동시에 코드, 설명서 및 식 평가 컨텍스트 내에서 작동 방법에 대해 설명 합니다. 세 가지 컨텍스트, 위치, 위치 또는 그와 관련 된 계산의 각각에 대해 설명합니다.  
  
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)  
 프로그램을 시작 하 여 식을 계산 등의 다양 한 디버깅 작업에 대 한 링크를 포함 합니다.