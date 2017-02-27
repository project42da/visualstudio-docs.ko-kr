---
title: "IDebugPointerObject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPointerObject"
helpviewer_keywords: 
  - "IDebugPointerObject 인터페이스"
ms.assetid: 257fa167-b46e-4ffb-9a12-272efbf26702
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugPointerObject
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 이 인터페이스는 포인터 개체를 나타냅니다.  
  
## 구문  
  
```  
IDebugPointerObject : IDebugObject  
```  
  
## 구현자를 위한 정보  
 식 계산기는 포인터 개체를 나타내는 데이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 인터페이스를 사용 하 여이 인터페이스를 가져올 수 [QueryInterface](/visual-cpp/atl/queryinterface) 경우는 `IDebugObject` 포인터를 나타냅니다.  
  
## Vtable 순서의 메서드  
 상속 된 메서드 외에도 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md),  `IDebugPointerObject` 인터페이스는 다음 메서드를 노출 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[역참조](../../../extensibility/debugger/reference/idebugpointerobject-dereference.md)|인터페이스 가리키는 개체를 가져옵니다.|  
|[GetBytes](../../../extensibility/debugger/reference/idebugpointerobject-getbytes.md)|인터페이스를 일련의 연속 된 바이트를 가리키는 값을 가져옵니다.|  
|[SetBytes](../../../extensibility/debugger/reference/idebugpointerobject-setbytes.md)|인터페이스를 일련의 연속 된 바이트를 가리키는 값을 설정 합니다.|  
  
## 설명  
 식 계산기는이 인터페이스를 사용 하 여 구문 분석 트리에 대 한 포인터를 나타냅니다.  
  
## 요구 사항  
 헤더: ee.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [식 평가 인터페이스](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)