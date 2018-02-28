---
title: IVariantChangeType::ChangeType | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IVariantChangeType.ChangeType
apilocation:
- scrobj.dll
helpviewer_keywords:
- IVariantChangeType::ChangeType
ms.assetid: 52374764-c42e-49af-a219-ee00c535a118
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d742d1bd57c85aa75c9ccd60479d08c1a559fb37
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ivariantchangetypechangetype"></a>IVariantChangeType::ChangeType
Variant 값을 사용 하 고 지정 된 유형의 새 variant를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ChangeType(  
   VARIANT*  pvarDst,  
   VARIANT*  pvarSrc,  
   LCID  lcid,  
   VARTYPE  vtNew  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pvarDst`  
 [out에서] 이 나타내는 값을 포함 하는 variant `pvarSrc`, 하지만에서 지정 된 형식의 `vtNew`합니다.  
  
 `pvarSrc`  
 [in] 새 형식으로 변경 하는 variant 값입니다.  
  
 `lcid`  
 [in] 문자열에서 인수를 변환할 때 사용할 로캘 컨텍스트.  
  
 `vtNew`  
 [in] 유형을 지정 `pvarDst` 되도록 합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 `pvarDst` 및 `pvarSrc` 인수가 필요할 수 이상이 면이 경우 원래 값을 덮어씁니다. 이 메서드는 전달 `pvarDst` 에 `VariantClear` 함수와 비슷하게 `pvarDst` 유효한 값으로 초기화 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IVariantChangeType 인터페이스](../../winscript/reference/ivariantchangetype-interface.md)