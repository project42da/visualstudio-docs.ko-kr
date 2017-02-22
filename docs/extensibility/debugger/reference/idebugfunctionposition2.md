---
title: "IDebugFunctionPosition2 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugFunctionPosition2"
helpviewer_keywords: 
  - "IDebugFunctionPosition2 인터페이스"
ms.assetid: a835f65b-91b0-48ad-8485-04534c814b1b
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugFunctionPosition2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 추상 함수 위치를에서 원본 문서를 나타냅니다.  
  
## 구문  
  
```  
IDebugFunctionPosition2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 함수 소스 문서 내에서 위치를 나타내는 데이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스의 일부로 제공 되는 [BP\_LOCATION](../../../extensibility/debugger/reference/bp-location.md) union \(구체적으로 [BP\_LOCATION\_CODE\_FUNC\_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md) 구조\)가 차례로의 일부입니다의 [BP\_REQUEST\_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 보류 중단점을 만드는 데 사용 되는 구조를.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugFunctionPosition2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetFunctionName](../../../extensibility/debugger/reference/idebugfunctionposition2-getfunctionname.md)|이 위치를 기준으로 된 함수의 이름을 가져옵니다.|  
|[GetOffset](../../../extensibility/debugger/reference/idebugfunctionposition2-getoffset.md)|함수 시작 부분에서 오프셋을 가져옵니다.|  
  
## 설명  
 이 인터페이스에 의해 표시 되는 위치를 텍스트 기반 특히입니다 있는 [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md) 구조.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [BP\_LOCATION\_CODE\_FUNC\_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md)   
 [BP\_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md)