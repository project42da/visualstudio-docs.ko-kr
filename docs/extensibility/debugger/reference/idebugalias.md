---
title: "IDebugAlias | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugAlias"
helpviewer_keywords: 
  - "IDebugAlias 인터페이스"
ms.assetid: 3cc4c9a4-7805-4239-b00e-eb4a024f3c55
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# IDebugAlias
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 변수에 대 한 숫자 별칭을 나타냅니다. 별칭은 변수에 대 한 다른 이름을 하기만 합니다.  
  
## 구문  
  
```  
IDebugAlias : IUnknown  
```  
  
## 구현자를 위한 정보  
 식 계산기 \(EE\) 변수에 대 한 숫자 별칭을 지원 하기 위해이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 [CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md) 특정 개체에 대 한 별칭을 만듭니다. 사용 하 여 별칭을 검색 하려면 [FindAlias](../../../extensibility/debugger/reference/idebugbinder3-findalias.md) 또는 [GetAllAliases](../../../extensibility/debugger/reference/idebugbinder3-getallaliases.md)합니다.  
  
## Vtable 순서의 메서드  
 다음 방법에 정의 된는 `IDebugAlias` 인터페이스입니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetObject](../../../extensibility/debugger/reference/idebugalias-getobject.md)|이 별칭이 참조 하는 개체를 가져옵니다.|  
|[GetName](../../../extensibility/debugger/reference/idebugalias-getname.md)|별칭 이름을 가져옵니다.|  
|[GetICorDebugValue](../../../extensibility/debugger/reference/idebugalias-geticordebugvalue.md)|검색 된 `ICorDebugValue` 인터페이스에 대 한 액세스를 제공 하는이 개체 \(관리 코드에만 해당\)에 대 한 코드 정보를 관리 합니다.|  
|[Dispose](../../../extensibility/debugger/reference/idebugalias-dispose.md)|더 이상으로 별칭 사용이 표시 됩니다.|  
  
## 설명  
 별칭은, 예를 들어 1001 \# \# 문자를 문자열 형식으로 10 진수입니다.  
  
## 요구 사항  
 헤더: ee.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [식 평가 인터페이스](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md)   
 [FindAlias](../../../extensibility/debugger/reference/idebugbinder3-findalias.md)   
 [GetAllAliases](../../../extensibility/debugger/reference/idebugbinder3-getallaliases.md)