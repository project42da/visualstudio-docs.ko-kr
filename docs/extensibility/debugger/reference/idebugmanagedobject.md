---
title: IDebugManagedObject | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugManagedObject
helpviewer_keywords:
- IDebugManagedObject interface
ms.assetid: 3ae09d34-112c-4285-80ee-9f7f8dc414d7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a7127d2583093ae06b52712cc6aacb0ea1adffc8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugmanagedobject"></a>IDebugManagedObject
> [!IMPORTANT]
>  Visual Studio 2015에서 구현 하는 식 계산기의 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 이 인터페이스 (EE) 값 클래스 인스턴스의 속성 또는 메서드를 호출 하는 식 계산기를 수 있습니다. (예를 들어 `System.Decimal`) 호출 하지 않고 해당 값을 설정 하 고 [평가](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md) 디버깅 중인 프로그램에 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugManagedObject : IDebugObject  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 식 계산기는 변수와 같은 관리 코드 개체를 나타내는 데이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 인터페이스를 가져오려면 호출 [GetManagedDebugObject](../../../extensibility/debugger/reference/idebugobject-getmanageddebugobject.md) 에 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 값 클래스의 인스턴스를 나타내는입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 상속 된 메서드 외에도 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md), `IDebugManagedObject` 인터페이스는 다음 메서드를 노출 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject-getmanagedobject.md)|모든 적절 한 관리 되는 코드에서 인터페이스를 가져올 수 있습니다 및 관리 코드 개체를 나타내는 인터페이스를 반환 합니다.|  
|[SetFromManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject-setfrommanagedobject.md)|관리 되는 코드를 지정 된 개체의 값이 개체의 값을 설정합니다.|  
  
## <a name="remarks"></a>설명  
 식 계산기 구문 분석 트리에 관리 되는 코드 개체를 저장 하려면이 인터페이스를 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [식 평가 인터페이스](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [평가](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md)