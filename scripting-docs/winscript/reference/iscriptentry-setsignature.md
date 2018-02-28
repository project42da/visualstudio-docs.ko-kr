---
title: IScriptEntry::SetSignature | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IScriptEntry.SetSignature
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::SetSignature
ms.assetid: 8513587d-9df2-4621-afe7-56eacbb5e688
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c9ff480f8e5c3192a7e2b355d39825cc3a084370
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iscriptentrysetsignature"></a>IScriptEntry::SetSignature
집합 형식에 대 한 정보는 `IScriptEntry` 함수 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetSignature(  
   ITypeInfo          *pti  
   ULONG              iMethod  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pti`  
 [in] 유형 정보입니다.  
  
 `iMethod`  
 [in] 메서드 인덱스는 `ITypeInfo` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 형식 정보를 사용 하 여 설정한 `IScriptEntry::SetSignature` 또는 [IScriptNode::CreateChildHandler](../../winscript/reference/iscriptnode-createchildhandler.md)합니다. 함수 내부 표현에 따라 항목으로 형식 정보를 생성할 수도 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)