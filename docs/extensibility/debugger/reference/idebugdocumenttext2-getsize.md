---
title: IDebugDocumentText2::GetSize | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugDocumentText2::GetSize
helpviewer_keywords:
- IDebugDocumentText2::GetSize
ms.assetid: bf515a8f-dcee-4004-8f81-543d547ceaae
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 117d557ad2ee5d7fe3490644162d1995e86c1873
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdocumenttext2getsize"></a>IDebugDocumentText2::GetSize
문서의이 위치에서 텍스트의 크기를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetSize(   
   ULONG* pcNumLines,  
   ULONG* pcNumChars  
);  
```  
  
```csharp  
int GetSize(   
   ref uint pcNumLines,  
   ref uint pcNumChars  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pcNumLines`  
 [out] 텍스트의 줄 수를 반환합니다.  
  
 `pcNumChars`  
 [out] 텍스트의 문자 수를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 [C + + 전용] 특정 값이 적절 하지 않으면 매개 변수에 대해 NULL 값을 전달 합니다.  
  
 [C#] 두 매개 변수를 지정 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)