---
title: "IActiveScriptError::GetSourcePosition | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptError.GetSourcePosition
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptError_GetSourcePosition"
ms.assetid: ae9b26b1-82a7-4645-9686-3261d8248664
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScriptError::GetSourcePosition
스크립팅 엔진이 스크립트를 실행 하는 동안 오류가 발생 한 위치 위치에서 소스 코드를 검색 합니다.  
  
## 구문  
  
```  
HRESULT GetSourcePosition(  
    DWORD *pdwSourceContext,  // context cookie  
    ULONG *pulLineNumber,     // line number of error  
    LONG *pichCharPosition    // character position of error  
);  
```  
  
#### 매개 변수  
 `pdwSourceContext`  
 \[out\] 주소 변수는 컨텍스트를 식별 하는 쿠키를 받습니다.  이 매개 변수는 해석 호스트 응용 프로그램에 따라 달라 집니다.  
  
 `pulLineNumber`  
 \[out\] 주소 오류가 발생 한 소스 파일에서 줄 번호를 받는 변수입니다.  
  
 `pichCharPosition`  
 \[out\] 변수의 주소를 받는 줄 문자 위치 오류가 발생 합니다.  
  
## 반환 값  
 반환 `S_OK` 면 또는 `E_FAIL` 위치 검색 된 경우.  
  
## 참고 항목  
 [IActiveScriptError](../../winscript/reference/iactivescripterror.md)