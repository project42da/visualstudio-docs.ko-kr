---
title: "IDebugGenericFieldInstance::TypeArgumentCount | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "TypeArgumentCount"
  - "IDebugGenericFieldInstance::TypeArgumentCount"
ms.assetid: e662c5ea-a5c1-478e-a268-5980dadffcd1
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugGenericFieldInstance::TypeArgumentCount
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인스턴스에 대 한 매개 변수 인수 유형 수를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT TypeArgumentCount(  
   ULONG32* pcArgs  
);  
```  
  
```c#  
int TypeArgumentCount(  
   ref uint pcArgs  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pcArgs`  
 [에서, out] 이 인스턴스에 대 한 형식 매개 변수 인수의 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>주의  
 예를 들어 경우 목록 \< int>, 이 메서드는 1을 반환 하며, 목록 \< int, float2 >이 메서드는 2를 반환 합니다. 이 메서드는 형식 인수가 있을 경우 0을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugGenericFieldInstance](../../../extensibility/debugger/reference/idebuggenericfieldinstance.md)