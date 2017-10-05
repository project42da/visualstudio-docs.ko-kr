---
title: IDebugArrayObject2::GetBaseIndices | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GetBaseIndices
- IDebugArrayObject2::GetBaseIndices
ms.assetid: 882951a2-3da0-49bf-8d1e-7daedd13ffe6
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 3aa9ad51de0f929083457eed86d69cf23f99d10d
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="idebugarrayobject2getbaseindices"></a>IDebugArrayObject2::GetBaseIndices
배열의 차원 수를 지정 된 각 인덱스에 대 한 기본 인덱스 (하위 범위)를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetBaseIndices (  
   DWORD  dwRank,  
   DWORD* dwIndices  
);  
```  
  
```csharp  
int GetBaseIndices (  
   uint       dwRank,  
   out uint[] dwIndices  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwRank`  
 [in] 배열의 차수 (rank)의 수입니다.  
  
 `dwIndices`  
 [out] 배열에 대 한 기본 인덱스 (하한값).  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 예를 들어,이 함수는 다음 C# 코드에서 만든 배열에 대 한 ' 5'를 반환 합니다.  
  
```  
int[] lengths = { 12 };  
int[] lowerbounds = { 5 };  
Array.CreateInstance(typeof(int), lengths, lowerbounds);  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDebugArrayObject2](../../../extensibility/debugger/reference/idebugarrayobject2.md)
