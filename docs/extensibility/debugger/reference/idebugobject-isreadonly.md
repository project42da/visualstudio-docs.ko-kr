---
title: IDebugObject::IsReadOnly | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugObject::IsReadOnly
helpviewer_keywords: IDebugObject::IsReadOnly method
ms.assetid: c460f772-d08a-4b36-81f3-dff6a51a93fd
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f1bcd4dc3f23a5305a2b40ee19affb8ae28ffd6f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugobjectisreadonly"></a>IDebugObject::IsReadOnly
이 개체는 읽기 전용으로 설정 하는 경우를 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsReadOnly(   
   BOOL* pfIsReadOnly  
);  
```  
  
```csharp  
int IsReadOnly(  
   out int pfIsReadOnly  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pfIsReadOnly`  
 [out] 0이 아닌 반환 (`TRUE`)이이 개체는 읽기 전용이 아니면이 아니면 0이 반환 (`FALSE`).  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 읽기 전용 개체를 만든 후 변경 된 값을 가질 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)