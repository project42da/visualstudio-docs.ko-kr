---
title: IRemoteDebugApplicationEx:SetLocale | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IRemoteDebugApplicationEx:SetLocale
apilocation: scrobj.dll
helpviewer_keywords: IRemoteDebugApplicationEx:SetLocale
ms.assetid: cd19f725-f4cd-453a-95e1-0bad676451da
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 19b2d58974e7da7bd40dad1faa9e361b0327e4c6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iremotedebugapplicationexsetlocale"></a>IRemoteDebugApplicationEx:SetLocale
디버거 지역화에 대 한 언어를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetLocale(  
   DWORD  dwLangID  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwLangID`  
 [in] 언어 id입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [ISetNextStatement 인터페이스](../../winscript/reference/isetnextstatement-interface.md)