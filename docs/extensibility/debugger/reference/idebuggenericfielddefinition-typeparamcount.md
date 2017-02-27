---
title: "IDebugGenericFieldDefinition::TypeParamCount | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "TypeParamCount"
  - "IDebugGenericFieldDefinition::TypeParamCount"
ms.assetid: d41dd5ea-aa25-4bf3-bcfd-e0bf451ead49
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugGenericFieldDefinition::TypeParamCount
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

일반 필드와 연결 된 형식 매개 변수 개수를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT TypeParamCount(  
   ULONG32* pcParams  
);  
```  
  
```c#  
int TypeParamCount(  
   ref uint pcParams  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pcParams`  
 [에서, out] 형식 매개 변수 개수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>주의  
 경우 목록 \< T>, 이 메서드는 1을 반환 하며, \< T1, T2 > 목록이이 메서드는 2를 반환 합니다. 이 메서드는 형식 매개 변수가 없는 경우 0을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugGenericFieldDefinition](../../../extensibility/debugger/reference/idebuggenericfielddefinition.md)