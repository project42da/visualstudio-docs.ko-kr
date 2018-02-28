---
title: IDebugFunctionObject::CreateObject | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugFunctionObject::CreateObject
helpviewer_keywords:
- IDebugFunctionObject::CreateObject method
ms.assetid: c4c99dd5-609a-4e7c-8f29-eb728f57e995
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: b0b9a36dfac48d86963db68c3ab68500d8b8bfba
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugfunctionobjectcreateobject"></a>IDebugFunctionObject::CreateObject
생성자를 사용 하는 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateObject(   
   IDebugFunctionObject* pConstructor,  
   DWORD                 dwArgs,  
   IDebugObject*         pArgs[],  
   IDebugObject**        ppObject  
);  
```  
  
```csharp  
int CreateObject(  
   IDebugFunctionObject pConstructor,   
   uint                 dwArgs,   
   IDebugObject[]       pArgs,   
   out IDebugObject     ppObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pConstructor`  
 [in] [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 만들 개체의 생성자를 나타내는 개체입니다.  
  
 `dwArgs`  
 [in] 매개 변수 개수는 `pArg` 배열입니다. 생성자에 전달 된 매개 변수의 수를 나타냅니다.  
  
 `pArg`  
 [in] 배열을 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 생성자에 전달 된 매개 변수를 나타내는 개체입니다.  
  
 `ppObject`  
 [out] 반환 된 `IDebugObject` 새로 만든된 개체를 표시 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 클래스 (또는 생성자가 필요 하는 다른 복합 형식)의 인스턴스를 나타내는 개체를 만들려면이 메서드를 호출 즉으로 표시 된 함수에 매개 변수는 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 인터페이스입니다.  
  
 개체 매개 변수는 생성자에 필요 하지 않으면 경우 호출 된 [CreateObjectNoConstructor](../../../extensibility/debugger/reference/idebugfunctionobject-createobjectnoconstructor.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)   
 [CreateObjectNoConstructor](../../../extensibility/debugger/reference/idebugfunctionobject-createobjectnoconstructor.md)