---
title: IPerPropertyBrowsing2::GetDisplayString | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IPerPropertyBrowsing2.GetDisplayString
apilocation:
- scrobj.dll
helpviewer_keywords:
- IPerPropertyBrowsing2::GetDisplayString
ms.assetid: 8f75c6a9-86a9-4e2d-8cb4-74e7b1c0a524
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: be6f665d1f63966b3828868f4fb8fbf1cae002e9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iperpropertybrowsing2getdisplaystring"></a>IPerPropertyBrowsing2::GetDisplayString
Gets 기본적으로 표시 되지 않는 형식을 반환 되는 텍스트를 표시 하는 문자열 속성을 설명 하는 이름 및 호출자의 사용자 인터페이스에 표시 될 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetDisplayString(  
   DISPID  dispid,  
   BSTR*  pBstr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dispid`  
 [in] 표시 이름이 요청 된 속성의 식별자를 발송 합니다.  
  
 `pBstr`  
 [out] 에 대 한 포인터는 `BSTR` 로 식별 된 속성에 대 한 표시 이름을 포함 하 `dispID`합니다.  
  
## <a name="return-value"></a>반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`합니다.  
  
## <a name="remarks"></a>설명  
 반환 된 문자열 속성의 올바른 값 않습니다. 것 속성의 문자열 표시 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IPerPropertyBrowsing2 인터페이스 1](../../winscript/reference/iperpropertybrowsing2-interface-1.md)