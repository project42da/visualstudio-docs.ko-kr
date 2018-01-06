---
title: IDebugGenericFieldDefinition::TypeParamCount | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TypeParamCount
- IDebugGenericFieldDefinition::TypeParamCount
ms.assetid: d41dd5ea-aa25-4bf3-bcfd-e0bf451ead49
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 1df4aab215290f976f58f2c06f3cd42282344fee
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggenericfielddefinitiontypeparamcount"></a>IDebugGenericFieldDefinition::TypeParamCount
일반 필드와 연결 된 형식 매개 변수 수를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT TypeParamCount(  
   ULONG32* pcParams  
);  
```  
  
```csharp  
int TypeParamCount(  
   ref uint pcParams  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pcParams`  
 [out에서] 형식 매개 변수 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 경우 목록\<T >,이 메서드가 반환 1, 및 경우 목록\<T1, T2 >, 2이이 메서드를 반환 합니다. 이 메서드 형식 매개 변수가 없는 경우 0을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugGenericFieldDefinition](../../../extensibility/debugger/reference/idebuggenericfielddefinition.md)