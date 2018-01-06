---
title: IDebugProcess3::GetEngineFilter | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GetEngineFilter
- IDebugProcess3::GetEngineFilter
ms.assetid: ccb7ecb0-f189-4e80-b5b2-221a095e01f5
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 57a57341ba9df9333439c4acef2216821bc627a6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprocess3getenginefilter"></a>IDebugProcess3::GetEngineFilter
사용할 수 있는 디버그 엔진에 대 한 고유 식별자의 배열을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetEngineFilter(  
   GUID_ARRAY *pEngineArray  
);  
```  
  
```csharp  
public int GetEngineFilter(  
   out GUID_ARRAY[] pEngineArray  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pEngineArray`  
 [out] 디버그 엔진에 대 한 고유 식별자가 포함 된 구조에 대 한 참조입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [GUID_ARRAY](../../../extensibility/debugger/reference/guid-array.md)