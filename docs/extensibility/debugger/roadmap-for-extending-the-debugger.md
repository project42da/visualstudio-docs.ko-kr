---
title: "디버거를 확장 하기 위한 로드맵 | Microsoft Docs"
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
  - "디버깅 [디버깅 SDK] 로드맵"
  - "디버깅 SDK, 로드맵"
ms.assetid: 1f4096a8-f7aa-4dfa-84e1-6d59263e70bb
caps.latest.revision: 16
caps.handback.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
---
# 디버거를 확장 하기 위한 로드맵
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 설명서를 확장 하기 위한 가이드 및 참조 정보 제공은 [!INCLUDE[vs_current_short](../../code-quality/includes/vs_current_short_md.md)] 와 디버거는 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)].  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]디버깅 설명서, 샘플, 포괄적인 참조 및 디버거를 사용자 지정 하는 일반적인 방법을 보여 주는 몇 가지 대표적인 시나리오 포함 됩니다.  
  
 컴파일러 출력을 하 고 제품의 디버깅을 구현 하는 데 필요한 결정 합니다.  하는 경우 해당 컴파일러:  
  
-   Windows 기본 운영 체제를 대상으로 하 고 기록 된.PDB 파일을 수 있는 디버그 프로그램에 통합 하는 네이티브 코드 디버그 엔진 \(DE\)와 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  DE 또는 식 계산기를 구현 하지 않아도 됩니다.  식 계산기는 c \+ \+ 프로그래밍 언어의 구문에 대 한 기록 됩니다.  
  
-   Microsoft 중간 언어 \(MSIL\)를 출력할 수 있는 디버그 프로그램에도 통합 된 관리 되는 코드 디버그 엔진 DE 만듭니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  따라서 식 계산기 에서만 구현 해야 합니다.  샘플 식 계산기를 제공 합니다.  자세한 내용은 다음 항목을 참조하십시오.  
  
     [식 계산](../../extensibility/debugger/expression-evaluation-visual-studio-debugging-sdk.md)  
  
     [식 계산](../../extensibility/debugger/evaluating-expressions.md)  
  
     [식 평가 컨텍스트](../../extensibility/debugger/expression-evaluation-context.md)  
  
     [중단 모드에서 식 평가](../../extensibility/debugger/expression-evaluation-in-break-mode.md)  
  
     [공용 언어 런타임에서 식 계산기를 작성](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)  
  
-   대상 독점적 운영 체제 또는 다른 런타임 환경에서 직접 DE를 작성 해야 합니다.  ATL COM을 사용 하는 간단한 DE 만드는 대 한 자습서를 제공 합니다.  자세한 내용은 다음 항목을 참조하십시오.  
  
     [사용자 지정 디버그 엔진을 만들기](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
  
     [자습서: ATL COM을 사용 하는 디버그 엔진 구축](http://msdn.microsoft.com/ko-kr/9097b71e-1fe7-48f7-bc00-009e25940c24)  
  
     [포트 공급자 구현](../../extensibility/debugger/implementing-a-port-supplier.md)  
  
     [샘플](../../extensibility/debugger/visual-studio-debugging-samples.md)  
  
## 참고 항목  
 [시작](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)