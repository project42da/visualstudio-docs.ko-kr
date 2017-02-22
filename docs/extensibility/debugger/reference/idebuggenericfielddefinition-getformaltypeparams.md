---
title: "IDebugGenericFieldDefinition::GetFormalTypeParams | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "GetFormalTypeParams"
  - "IDebugGenericFieldDefinition::GetFormalTypeParams"
ms.assetid: cadbd6a1-bc7c-4aff-8777-5396b7a23c3e
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugGenericFieldDefinition::GetFormalTypeParams
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

매개 변수 개수를 지정 된 형식 매개 변수를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetFormalTypeParams(  
   ULONG32                   cParams,  
   IDebugGenericParamField** ppParams,  
   ULONG32*                  pcParams  
);  
```  
  
```c#  
int GetFormalTypeParams(  
   uint                          cParams,  
   out IDebugGenericParamField[] ppParams,  
   ref uint                      pcParams  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cParams`  
 [in] 매개 변수 개수입니다.  
  
 `ppParams`  
 [out] 배열 형식 매개 변수입니다.  
  
 `pcParams`  
 [에서, out] 매개 변수 수는 `ppParams` 배열입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>주의  
 오른쪽으로 왼쪽에서 순서 대로 형식 매개 변수를 반환 합니다. 예를 들어 \< K, V > 사전 IDebugFormalGenericParameters {K, V}를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugGenericFieldDefinition](../../../extensibility/debugger/reference/idebuggenericfielddefinition.md)