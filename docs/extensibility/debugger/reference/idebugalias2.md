---
title: "IDebugAlias2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugAlias2 인터페이스"
ms.assetid: 5252dcbb-8bfe-4d8a-a8e5-b022b194df19
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugAlias2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 숫자 변수에 별칭을 나타내며 식 계산기는 별칭에 대 한 응용 프로그램 도메인을 가져오려면 \(EE\)을 수 있습니다.  
  
## 구문  
  
```  
IDebugAlias2 : IDebugAlias  
```  
  
## 구현자를 위한 정보  
 이 인터페이스는 관리 되는 디버그 엔진 \(DE\)에 의해 구현 됩니다.  
  
## 메서드  
 메서드 외에 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md) 인터페이스를이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetAppDomainId](../../../extensibility/debugger/reference/idebugalias2-getappdomainid.md)|응용 프로그램 도메인에 대 한 식별자를 검색합니다.|  
  
## 설명  
 별칭은, 예를 들어 1001 \# \# 문자를 문자열 형식으로 10 진수입니다.  
  
## 요구 사항  
 헤더: Ee.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll