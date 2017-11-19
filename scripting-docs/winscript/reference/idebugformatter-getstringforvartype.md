---
title: IDebugFormatter::GetStringForVarType | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugFormatter.GetStringForVarType
apilocation: jscript.dll
helpviewer_keywords: IDebugFormatter::GetStringForVarType
ms.assetid: 1c1a0499-ca57-47e0-8367-fdb4c902bca3
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9e056fa2ef9613c1af776840d1dae61078e26f83
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugformattergetstringforvartype"></a>IDebugFormatter::GetStringForVarType
지정한 VARTYPE 값을 나타내는 문자열을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetStringForVarType(  
   VARTYPE    vt,  
   TYPEDESC*  ptdescArrayType,  
   BSTR*      pbstr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `vt`  
 [in] VARTYPE string으로 나타낼 수 있습니다.  
  
 `ptdescArrayType`  
 [in] 형식에 설명 하는 구조체의 배열입니다.  
  
 `pbstr`  
 [out] 문자열을 나타내는 `vt`합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 메서드는 지정한 VARTYPE 값을 나타내는 문자열을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugFormatter 인터페이스](../../winscript/reference/idebugformatter-interface.md)