---
title: IDebugObject::IsNullReference | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugObject::IsNullReference
helpviewer_keywords: IDebugObject::IsNullReference method
ms.assetid: 6dbfcdb0-954f-4486-8fac-7ea8d003e3a9
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1c1d9fec58fb8c5a47e08fac76f49d366cac3a37
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugobjectisnullreference"></a>IDebugObject::IsNullReference
이 개체는 null 참조 인지 테스트 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsNullReference(   
   BOOL* pfIsNull  
);  
```  
  
```csharp  
int IsNullReference(  
   out int pfIsNull  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pfIsNull`  
 [out] 0이 아닌 반환 (`TRUE`)이이 개체는 null 참조입니다; 그렇지 않으면 0이 반환 (`FALSE`).  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 Null 참조는 빈 개체 또는 개체에 할당 되지 않은 의미 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)