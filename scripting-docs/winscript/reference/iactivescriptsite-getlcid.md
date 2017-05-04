---
title: "IActiveScriptSite::GetLCID | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptSite.GetLCID
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptSite_GetLCID"
ms.assetid: 7b4a2dc1-bcf6-4bbf-884e-97b305a28eb7
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScriptSite::GetLCID
호스트의 사용자 인터페이스와 관련 된 로캘 식별자를 검색 합니다.  스크립팅 엔진에 적절 한 언어 엔진에서 생성 하는 다른 사용자 인터페이스 요소와 오류 문자열 표시 되도록 식별자를 사용 합니다.  
  
## 구문  
  
```  
HRESULT GetLCID(  
    LCID *plcid  // address of variable for language identifier  
);  
```  
  
#### 매개 변수  
 `plcid`  
 \[out\] 스크립팅 엔진에 의해 표시 되는 사용자 인터페이스 요소에 대 한 로캘 식별자를 받는 변수에 대 한 주소입니다.  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|성공|  
|`E_NOTIMPL`|이 메서드가 구현되지 않은 경우  시스템에 정의 된 로케일을 사용 합니다.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
  
## 설명  
 이 메서드가 반환 하는 경우 `E_NOTIMPL`, 시스템 정의 하는 로캘 식별자를 사용 해야 합니다.  
  
## 참고 항목  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)