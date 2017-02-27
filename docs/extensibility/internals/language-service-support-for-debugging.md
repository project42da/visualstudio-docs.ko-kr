---
title: "디버깅 하기 위한 언어 서비스 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버거를 언어 지원"
  - "언어 서비스, 디버깅 지원"
ms.assetid: 7a44067f-a410-4a6a-84d2-bda5184140bc
caps.latest.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 15
---
# 디버깅 하기 위한 언어 서비스 지원
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

언어 서비스를 통해 디버거 지원 기능을 제공할 수는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageDebugInfo> 인터페이스입니다. 이러한 기능에는 중단점의 유효성을 검사 하 고 제공 하는 식의 목록이 포함 된 **자동** 창입니다.  
  
 그러나 사용자의 언어를 디버깅 하는 식 계산기를 마련해 야 합니다. 식 계산기는 디버깅 하는 동안 값을 생성 하는 식을 계산 하는 일을 담당 합니다. CLR 식 계산기를 구현 하는 방법에 대 한 내용은 다음을 참조 하십시오.  
  
-   [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)  
  
-   [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)  
  
## 컴파일러 출력  
 컴파일러의 형식은 해당 언어에 대해 디버깅을 구현 하는 데 필요한 것을 결정 합니다. 컴파일러는 Windows 운영 체제를 대상으로 하.pdb 파일을 작성 하는 경우에 디버깅 엔진 Visual Studio에 통합 된 네이티브 코드와 프로그램을 디버깅할 수 있습니다. 중간 MSIL \(Microsoft language\)을 생성 하는 컴파일러 경우 디버깅 엔진으로, Visual Studio에도 통합 되어 관리 코드와 프로그램을 디버깅할 수 있습니다. 컴파일러는 독점 운영 체제 또는 다른 런타임 환경을 대상으로 하는 경우 고유한 디버깅 엔진을 작성 해야 합니다.  
  
 해당 언어에 대 한 디버깅 구현에 대 한 자세한 내용은 참조 하십시오. [시작](../../extensibility/debugger/getting-started-with-debugger-extensibility.md) Visual Studio 디버깅 SDK에 있습니다.