---
title: "IActiveScriptAuthor::GetEventHandler | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptAuthor.GetEventHandler
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptAuthor::GetEventHandler"
ms.assetid: 87c7a71d-46b9-448c-b34d-394105e20982
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# IActiveScriptAuthor::GetEventHandler
지정 된 특성을 가진 스크립트릿을 반환 합니다.  
  
## 구문  
  
```  
HRESULT GetEventHandler(  
   IDispatch          *pdisp,  
   LPCOLESTR          pszItem,  
   LPCOLESTR          pszSubItem,  
   LPCOLESTR          pszEvent,  
   IScriptEntry       **ppse  
);  
```  
  
#### 매개 변수  
 `pdisp`  
 \[in\] `IDispatch` 해당 개체는 `NamedItem` 는 스크립트릿 연결 됩니다.  
  
 `pszItem`  
 \[in\] 버퍼 주소 호스트에서 이름 정규화 스크립트릿 최상위 식별자입니다.  
  
 `pszSubItem`  
 \[in\] 버퍼 주소 호스트에서 이름 정규화 스크립트릿의 두 번째 수준 식별자입니다.  이름에 하나의 수준이 있는 경우 NULL로 설정 합니다.  
  
 `pszEvent`  
 \[in\] 이벤트 이름이 들어 있는 버퍼의 주소입니다.  스크립트릿은이 이벤트에 대 한 이벤트 처리기입니다.  
  
 `ppse`  
 \[out\] 에 대 한 포인터를 받는 변수의 주소는 `IScriptEntry` 인터페이스의 지정 된 특성을 가진 스크립트릿.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)   
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)