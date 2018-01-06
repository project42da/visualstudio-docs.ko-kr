---
title: IDebugBinder::GetMemoryContext | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugBinder::GetMemoryContext
helpviewer_keywords: IDebugBinder::GetMemoryContext method
ms.assetid: 801c5b60-acff-4822-b23d-e9c7bbca8a0f
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: cb26d2a7cad34743fe877dd4cca23170a0f087a9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugbindergetmemorycontext"></a>IDebugBinder::GetMemoryContext
이 메서드는 메모리 컨텍스트 개체 위치 이거나 메모리 주소를 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMemoryContext(   
   IDebugField*           pField,  
   DWORD                  dwConstant,  
   IDebugMemoryContext2** ppMemCxt  
);  
```  
  
```csharp  
int GetMemoryContext(  
   IDebugField              pField,   
   uint                     dwConstant,   
   out IDebugMemoryContext2 ppMemCxt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pField`  
 [in] [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 찾을 개체를 설명 하는 합니다. 경우 `NULL`를 사용 하 여 `dwConstant` 대신 합니다.  
  
 `dwConstant`  
 [in] 0x5000 같은 상수 메모리 주소입니다.  
  
 `ppMemCxt`  
 [out] 반환 된 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 개체의 주소 또는 메모리의 주소를 나타내는 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)