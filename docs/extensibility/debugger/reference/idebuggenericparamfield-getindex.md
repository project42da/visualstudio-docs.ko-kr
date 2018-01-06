---
title: IDebugGenericParamField::GetIndex | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugGenericParamField::GetIndex
ms.assetid: 8e0bdb26-1247-44d9-8d80-ec6e35187fb4
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 859764a8673c953e3a2dffa06219349e8f76db6a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggenericparamfieldgetindex"></a>IDebugGenericParamField::GetIndex
이 제네릭 매개 변수의 인덱스를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetIndex(  
   DWORD* pIndex  
);  
```  
  
```csharp  
int GetIndex(  
   out uint pIndex  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pIndex`  
 [out] 이 제네릭 매개 변수 인덱스 값입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 예를 들어 Dictionary(K,V)에 대 한 K는 인덱스 0, V는 인덱스 1입니다.  
  
## <a name="example"></a>예  
 다음 예제에 대 한이 메서드를 구현 하는 방법을 보여 줍니다는 **CDebugGenericParamFieldType** 공개 하는 개체는 [IDebugGenericParamField](../../../extensibility/debugger/reference/idebuggenericparamfield.md) 인터페이스입니다.  
  
```cpp  
HRESULT CDebugGenericParamFieldType::GetIndex(DWORD* pIndex)  
{  
    HRESULT hr = S_OK;  
  
    METHOD_ENTRY( CDebugGenericParamFieldType::GetIndex );  
  
    IfFalseGo(pIndex, E_INVALIDARG );  
    IfFailGo( this->LoadProps() );  
    *pIndex = m_index;  
  
Error:  
  
    METHOD_EXIT( CDebugGenericParamFieldType::GetIndex, hr );  
    return hr;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDebugGenericParamField](../../../extensibility/debugger/reference/idebuggenericparamfield.md)