---
title: "IDebugManagedObject | Microsoft Docs"
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
  - "IDebugManagedObject"
helpviewer_keywords: 
  - "IDebugManagedObject 인터페이스"
ms.assetid: 3ae09d34-112c-4285-80ee-9f7f8dc414d7
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugManagedObject
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 이 인터페이스를 사용 하는 식 계산기 \(EE\) 값 클래스 인스턴스의 속성 또는 메서드를 호출 하 \(예를 들어 `System.Decimal`\) 호출 하지 않고 해당 값을 설정 하 고 [평가](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md) 디버깅 중인 프로그램에 있습니다.  
  
## 구문  
  
```  
IDebugManagedObject : IDebugObject  
```  
  
## 구현자를 위한 정보  
 식 계산기는 변수와 같은 관리 코드 개체를 나타내는이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스를 가져오려면 호출 [GetManagedDebugObject](../../../extensibility/debugger/reference/idebugobject-getmanageddebugobject.md) 에 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 값 클래스의 인스턴스를 나타내는입니다.  
  
## Vtable 순서의 메서드  
 상속 된 메서드 외에도 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md),  `IDebugManagedObject` 인터페이스는 다음 메서드를 노출 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject-getmanagedobject.md)|관리 코드 개체를 나타내는 하 고 있는 모든 적절 한 관리 되는 코드에서 인터페이스를 가져올 수 있습니다 인터페이스를 반환 합니다.|  
|[SetFromManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject-setfrommanagedobject.md)|관리 되는 코드를 지정 된 개체의 값이 개체의 값을 설정합니다.|  
  
## 설명  
 식 계산기 구문 분석 트리에 관리 되는 코드 개체를 저장 하려면이 인터페이스를 사용 합니다.  
  
## 요구 사항  
 헤더: ee.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [식 평가 인터페이스](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [평가](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md)