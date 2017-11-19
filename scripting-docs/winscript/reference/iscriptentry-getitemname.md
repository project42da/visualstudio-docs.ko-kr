---
title: IScriptEntry::GetItemName | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IScriptEntry.GetItemName
apilocation: scrobj.dll
helpviewer_keywords: IScriptEntry::GetItemName
ms.assetid: 8f2562f1-8231-4a39-ad79-074f9ec3d403
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cdbb293afc6f58f8d9d9c1fe27bae467fd36792c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iscriptentrygetitemname"></a>IScriptEntry::GetItemName
식별 하는 항목 이름을 반환 하는 `IScriptEntry` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetItemName(  
   BSTR               *pbstr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstr`  
 [out] 항목 이름을 포함 하는 버퍼의 주소입니다. 항목 이름이 항목 식별 하기 위해 호스트에서 사용 됩니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 에 대 한 `IScriptScriptlet` 개체를 사용 하 여 항목 이름을 설정한 [IActiveScriptAuthor::AddScriptlet](../../winscript/reference/iactivescriptauthor-addscriptlet.md)합니다. 다른 인터페이스에 대 한 항목 이름을 사용 하 여 설정한 [IScriptEntry::SetItemName](../../winscript/reference/iscriptentry-setitemname.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)