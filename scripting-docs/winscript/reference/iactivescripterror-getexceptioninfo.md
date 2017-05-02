---
title: "IActiveScriptError::GetExceptionInfo | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptError.GetExceptionInfo
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptError_GetExceptionInfo"
ms.assetid: 528416cc-8468-4ad7-a6c2-fa1daf6ecf33
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScriptError::GetExceptionInfo
스크립팅 엔진이 스크립트를 실행 하는 동안 발생 한 오류에 대 한 정보를 검색 합니다.  
  
## 구문  
  
```  
HRESULT GetExceptionInfo(  
    EXCEPINFO *pexcepinfo  // structure for exception information  
);  
```  
  
#### 매개 변수  
 `pexcepinfo`  
 \[out\] 주소는 `EXCEPINFO` 오류 정보를 수신 하는 구조입니다.  
  
## 반환 값  
 반환 `S_OK` 면 또는 `E_FAIL` 오류가 발생 한 경우.  
  
## 참고 항목  
 [IActiveScriptError](../../winscript/reference/iactivescripterror.md)