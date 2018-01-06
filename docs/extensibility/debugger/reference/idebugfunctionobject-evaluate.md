---
title: IDebugFunctionObject::Evaluate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugFunctionObject::Evaluate
helpviewer_keywords: IDebugFunctionObject::Evaluate method
ms.assetid: 29349ea3-d5c1-4135-aa76-ced073ab9683
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a665f5db26955db2d3879e0d37c07efd3856bf68
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugfunctionobjectevaluate"></a>IDebugFunctionObject::Evaluate
함수를 호출 하 고 개체로 결과 값을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Evaluate(   
   IDebugObject** ppParams,  
   DWORD          dwParams,  
   DWORD          dwTimeout,  
   IDebugObject** ppResult  
);  
```  
  
```csharp  
int Evaluate(  
   IDebugObject[]   ppParams,   
   IntPtr           dwParams,   
   uint             dwTimeout,   
   out IDebugObject ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppParams`  
 [in] 배열을 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 입력된 매개 변수를 나타내는 개체입니다. 중 하나를 사용 하 여 만든 각 매개이 변수에 `Create` 의 메서드는 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 인터페이스입니다.  
  
 `dwParams`  
 [in] 매개 변수 개수는 `ppParams` 배열입니다.  
  
 `dwTimeout`  
 [in] 이 메서드로부터 반환 하기 전에 대기할 밀리초 단위로 최대 시간을 지정 합니다. 사용 하 여 `INFINITE` 무기한 대기를 나타냅니다.  
  
 `ppResult`  
 [out] 반환 된 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 함수 개체의 값을 나타내는입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 설정 하 고 호출 함수가을 실행 하는이 메서드는 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)