---
title: "IActiveScriptError::GetSourceLineText | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptError.GetSourceLineText
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptError_GetSourceLineText"
ms.assetid: 64f7f37f-7288-4dbe-b626-a35d90897f36
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScriptError::GetSourceLineText
스크립팅 엔진에는 스크립트를 실행 하는 동안 오류가 발생 한 위치는 소스 파일의 줄을 검색 합니다.  
  
## 구문  
  
```  
HRESULT GetSourceLineText(  
    BSTR *pbstrSourceLine  // address of buffer for source line  
);  
```  
  
## Parameter  
 `pbstrSourceLine`  
 \[out\] 오류가 발생 한 소스 코드의 줄을 받는 버퍼의 주소입니다.  
  
## 반환 값  
 반환 `S_OK` 면 또는 `E_FAIL` 줄 소스 파일에 검색 된 경우.  
  
## 참고 항목  
 [IActiveScriptError](../../winscript/reference/iactivescripterror.md)