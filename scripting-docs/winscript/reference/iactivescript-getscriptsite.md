---
title: "IActiveScript::GetScriptSite | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScript.GetScriptSite
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScript_GetScriptSite"
ms.assetid: 83a2a89d-93d0-4cbd-9244-91a730cb406b
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# IActiveScript::GetScriptSite
Windows 스크립트 엔진에 관련 된 사이트 개체를 검색 합니다.  
  
## 구문  
  
```  
HRESULT GetScriptSite(  
    REFIID iid,           // interface identifier  
    void **ppvSiteObject  // address of host site interface  
);  
```  
  
#### 매개 변수  
 `iid`  
 \[in\] 요청 된 인터페이스의 식별자입니다.  
  
 `ppvSiteObject`  
 \[out\] 주소는 호스트의 사이트 개체에 대 한 인터페이스 포인터를 받는 위치입니다.  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|성공|  
|`E_INVALIDARG`|인수가 잘못된 경우.|  
|`E_NOINTERFACE`|지정 된 인터페이스는 지원 되지 않습니다.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`S_FALSE`|설정 된 사이트가 없습니다. `ppvSiteObject` 매개 변수가 설정 되어 `NULL`.|  
  
## 참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)