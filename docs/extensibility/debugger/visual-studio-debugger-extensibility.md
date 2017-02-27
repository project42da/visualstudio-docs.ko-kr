---
title: "Visual Studio 디버거 확장성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [Visual Studio], SDK 디버깅"
  - "디버깅 SDK"
ms.assetid: c088b6a2-c3ad-446b-830d-9c6f41b2934b
caps.latest.revision: 32
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 32
---
# Visual Studio 디버거 확장성
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Visual Studio는 프로그램에서 버그를 추적 하기 위한 강력 하 고 사용 하기 쉬운 도구를 제공 하는 완전 한 대화형 소스 코드 디버거를 포함 합니다. 디버거는 완벽 한 지원이 Visual Basic, C\#, C\/c \+ \+ 및 JavaScript에 있습니다. 그러나는 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], 즉에서 사용할 수는 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/?LinkId=214453),, 디버거를 같은 다양 한 기능에는 다른 프로그래밍 언어를 지원할 수 있습니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버거 인 그러면 디버깅 중인 언어와 관련 된 디버깅 구성 일반적인 프런트 엔드 \(즉, 사용자 인터페이스\)가 있습니다. 새 언어에 대 한 하 여 지원에 필요한 모든는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버거는 디버그 엔진 \(DE\) 등 필요한 백 엔드 구성 요소를 만듭니다. 여기에서 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 제공 합니다.  
  
 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 모두에 대 한 전체 참조를 포함 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 새 파생을 만드는 데 필요한 요소입니다. 또한, 샘플 및 자습서를 시작 하는 데 도움이 되는.  
  
 디버깅 지원 언어 프로젝트 시스템의 종단 간 예제를 참조 하십시오.는 [IronPython sample](http://msdn.microsoft.com/ko-kr/4c41695c-12c1-4670-b43b-d8d84c9e4089)합니다.  
  
 다음 단원에서는 디버거를 사용 하 여 확장 하는 방법에 설명 된 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]합니다.  
  
## 단원 내용  
 [시작](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)  
 설명 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 특별 행사 및 SDK를 설치 하는 방법을 디버깅 합니다.  
  
 [사용자 지정 디버그 엔진 만들기](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 프로그램은 DE 분리를 DE 준비에서 사용자 지정 DE 절차에 설명 합니다.  
  
 [CLR 식 계산기를 작성합니다.](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)  
 식 계산기를 작성 해야 하는지 여부를 설명 합니다.  
  
 [디버그 엔진 구현 전략 선택](../../extensibility/debugger/choosing-a-debug-engine-implementation-strategy.md)  
 프로그램 DE를 구현 하는 방법에 설명 합니다.  
  
 [참조](../../extensibility/debugger/reference/reference-visual-studio-debugging-apis.md)  
 문서는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버깅 API입니다.  
  
 [샘플](../../extensibility/debugger/visual-studio-debugging-samples.md)  
 공용 언어 런타임 식 계산기 예제는 디버그 엔진 샘플에 대 한 링크를 포함합니다.