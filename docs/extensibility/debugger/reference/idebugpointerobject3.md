---
title: "IDebugPointerObject3 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugPointerObject3 인터페이스"
ms.assetid: 11d26af4-1079-435e-96fa-d5269cbea8eb
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugPointerObject3
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 구문 분석 트리에 대 한 포인터를 나타내며 확장은 **IDebugPointerObject** 인터페이스입니다.  
  
## 구문  
  
```  
IDebugPointerObject3 : IDebugPointerObject  
```  
  
## 구현자를 위한 정보  
 이 인터페이스를 구현 하는 식 계산기 \(EE\).  
  
## 메서드  
 메서드 외에 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetPointerAddress](../../../extensibility/debugger/reference/idebugpointerobject3-getpointeraddress.md)|포인터의 주소를 검색합니다.|  
  
## 요구 사항  
 헤더: Ee.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll