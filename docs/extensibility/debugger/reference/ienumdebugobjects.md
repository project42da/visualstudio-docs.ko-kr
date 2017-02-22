---
title: "IEnumDebugObjects | Microsoft Docs"
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
  - "IEnumDebugObjects"
helpviewer_keywords: 
  - "IEnumDebugObjects 인터페이스"
ms.assetid: 0950364c-6c8a-4b6c-ba37-c6aa359fa72c
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IEnumDebugObjects
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 이 인터페이스를 구현 하는 개체의 컬렉션을 나타냅니다는 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 인터페이스입니다.  
  
## 구문  
  
```  
IEnumDebugObjects : IUnknown  
```  
  
## 구현자를 위한 정보  
 구현 하는 개체 집합을 제공 하기 위해이 인터페이스를 구현 하는 식 계산기는 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 인터페이스입니다. 이 하지는 표준 COM 열거형으로 인해는 [GetCount](../../../extensibility/debugger/reference/ienumdebugobjects-getcount.md) 메서드.  
  
## 호출자에 대 한 참고 사항  
 [GetElements](../../../extensibility/debugger/reference/idebugarrayobject-getelements.md) 이 인터페이스를 반환합니다.  
  
## Vtable 순서의 메서드  
 이 인터페이스는 다음 메서드를 구현합니다.  
  
|메서드|설명|  
|---------|--------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugobjects-next.md)|다음 집합을 검색 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 열거에서 개체입니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugobjects-skip.md)|지정 된 항목 수를 건너뜁니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugobjects-reset.md)|열거형의 첫 번째 항목을 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugobjects-clone.md)|현재 열거형의 복사본을 검색 합니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugobjects-getcount.md)|열거형에는 항목 수를 검색합니다.|  
  
## 설명  
 이 인터페이스를 배열에 있는 개체의 집합에 대해 열거 하는 디버그 엔진을 사용 합니다.  
  
## 요구 사항  
 헤더: ee.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [GetElements](../../../extensibility/debugger/reference/idebugarrayobject-getelements.md)