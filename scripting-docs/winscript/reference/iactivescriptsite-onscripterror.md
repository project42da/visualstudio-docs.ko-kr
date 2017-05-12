---
title: "IActiveScriptSite::OnScriptError | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptSite.OnScriptError
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptSite_OnScriptError"
ms.assetid: 5c9c85cc-21ad-4232-be83-a24cc7570108
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScriptSite::OnScriptError
엔진은 스크립트를 실행 하는 동안 실행 오류가 발생 했음을 호스트에 게 알립니다.  
  
## 구문  
  
```  
HRESULT OnScriptError(  
    IActiveScriptError *pase  // address of error interface  
);  
```  
  
#### 매개 변수  
 `pase`  
 \[in\] Error 개체의 주소 [IActiveScriptError](../../winscript/reference/iactivescripterror.md) 인터페이스.  호스트는이 인터페이스 실행 오류에 대 한 정보를 얻을 수 있습니다.  
  
## 반환 값  
 반환 `S_OK` 오류를 제대로 처리 하거나 OLE 그렇지 않으면 오류 코드를 정의 합니다.  
  
## 참고 항목  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)