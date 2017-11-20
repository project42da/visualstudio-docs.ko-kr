---
title: IActiveScriptError::GetSourceLineText | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptError.GetSourceLineText
apilocation: scrobj.dll
helpviewer_keywords: IActiveScriptError_GetSourceLineText
ms.assetid: 64f7f37f-7288-4dbe-b626-a35d90897f36
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bb886d5f40042313483dc3b298488d1291c30563
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescripterrorgetsourcelinetext"></a>IActiveScriptError::GetSourceLineText
스크립팅 엔진을 스크립트를 실행 하는 동안 오류가 발생 한 소스 파일의 줄을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetSourceLineText(  
    BSTR *pbstrSourceLine  // address of buffer for source line  
);  
```  
  
## <a name="parameter"></a>매개 변수  
 `pbstrSourceLine`  
 [out] 오류가 발생 한 소스 코드의 줄에 받는 버퍼의 주소입니다.  
  
## <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 하면 또는 `E_FAIL` 소스 파일의 선을 검색 되지 않은 경우.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptError](../../winscript/reference/iactivescripterror.md)