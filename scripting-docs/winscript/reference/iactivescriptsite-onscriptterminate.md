---
title: "IActiveScriptSite::OnScriptTerminate | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptSite.OnScriptTerminate
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptSite_OnScriptTerminate"
ms.assetid: 3301ddf4-5929-404c-81d3-1a720e589008
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScriptSite::OnScriptTerminate
스크립트 실행을 완료 했음을 호스트에 게 알립니다.  
  
## 구문  
  
```  
HRESULT OnScriptTerminate(  
    VARIANT *pvarResult,   // address of script results  
    EXCEPINFO *pexcepinfo  // address of structure with exception information  
);  
```  
  
#### 매개 변수  
 `pvarResult`  
 \[in\] 스크립트 결과 포함 하는 변수의 주소 또는 `NULL` 스크립트가 없는 결과 생성 하는 경우.  
  
 `pexcepinfo`  
 \[in\] 주소는 `EXCEPINFO` 스크립트가 종료 되 면 생성 되는 예외 정보를 포함 하는 구조 또는 `NULL` 예외가 생성 되었습니다.  
  
## 반환 값  
 성공하면 `S_OK`를 반환합니다.  
  
## 설명  
 호출 하기 전에이 메서드를 호출 하는 스크립팅 엔진의 [IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md) 메서드와 SCRIPTSTATE\_INITIALIZED 플래그가 설정 되어 완료.  완료 상태 및 결과 호스트에 반환 하려면이 메서드를 사용할 수 있습니다.  호스트에서 이벤트를 싱크를 기반으로 하는 많은 스크립트 언어는 호스트에 의해 정의 된 사용 기간은 있는지 note입니다.  이 경우이 메서드가 호출 되지 않을 수 있습니다.  
  
## 참고 항목  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)