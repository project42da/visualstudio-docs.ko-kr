---
title: IDebugFunctionObject::CreateObjectNoConstructor | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugFunctionObject::CreateObjectNoConstructor
helpviewer_keywords: IDebugFunctionObject::CreateObjectNoConstructor method
ms.assetid: 4e2bd6d5-f4bd-4c10-a998-3db451c9a0c8
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 84fc96ae41827b06ffcb79a12276840cdf07cfac
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugfunctionobjectcreateobjectnoconstructor"></a>IDebugFunctionObject::CreateObjectNoConstructor
없는 생성자를 가진 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateObjectNoConstructor(   
   IDebugField*   pClassObject,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int CreateObjectNoConstructor(  
   IDebugField      pClassField,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pClassObject`  
 [in] [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 만들 개체의 형식을 나타내는 개체입니다.  
  
 `ppObject`  
 [out] 반환 된 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 새로 만든된 개체를 표시 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 구조 또는 복합 형식 (생성자 필요 없음)은 함수에 매개 변수는 요소로 표시 되는 인스턴스를 나타내는 개체를 만들려면이 메서드를 호출 하는 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 인터페이스입니다.  
  
 개체 매개 변수는 생성자가 필요한 경우 호출 된 [CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject-createobject.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)   
 [CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject-createobject.md)