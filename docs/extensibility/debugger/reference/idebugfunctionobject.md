---
title: "IDebugFunctionObject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugFunctionObject"
helpviewer_keywords: 
  - "IDebugFunctionObject 인터페이스"
ms.assetid: 8d94e97c-a9d1-400c-8a98-a44b5385b33a
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# IDebugFunctionObject
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 이 인터페이스는 함수를 나타냅니다.  
  
## 구문  
  
```  
IDebugFunctionObject : IDebugObject  
```  
  
## 구현자를 위한 정보  
 식 계산기는 함수를 나타내는 데이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스는의 특수화 된 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 인터페이스를 사용 하 여 가져온 [QueryInterface](/visual-cpp/atl/queryinterface) 에 `IDebugObject` 인터페이스입니다.  
  
## Vtable 순서의 메서드  
 상속 된 메서드 외에도 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md),  `IDebugFunctionObject` 인터페이스는 다음 메서드를 노출 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[CreatePrimitiveObject](../../../extensibility/debugger/reference/idebugfunctionobject-createprimitiveobject.md)|기본 데이터 개체를 만듭니다.|  
|[CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject-createobject.md)|생성자를 사용 하 여 개체를 만듭니다.|  
|[CreateObjectNoConstructor](../../../extensibility/debugger/reference/idebugfunctionobject-createobjectnoconstructor.md)|생성자가 없는와 개체를 만듭니다.|  
|[CreateArrayObject](../../../extensibility/debugger/reference/idebugfunctionobject-createarrayobject.md)|배열 개체를 만듭니다.|  
|[CreateStringObject](../../../extensibility/debugger/reference/idebugfunctionobject-createstringobject.md)|문자열 개체를 만듭니다.|  
|[평가](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md)|함수를 호출 하 고 결과 값으로 개체를 반환 합니다.|  
  
## 설명  
 이 인터페이스를 구문 분석 트리의 함수를 나타내는 식 계산기를 수 있습니다.`Create` 이 인터페이스의 메서드는 메서드에 입력된 매개 변수를 나타내는 개체를 생성 하는 데 사용 됩니다. 함수를 호출 하 여 실행할 수 있습니다는 [평가](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md) 메서드는 함수의 반환 값을 나타내는 개체를 반환 합니다.  
  
## 요구 사항  
 헤더: ee.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [식 평가 인터페이스](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)