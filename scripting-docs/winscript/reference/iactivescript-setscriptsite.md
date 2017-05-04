---
title: "IActiveScript::SetScriptSite | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScript.SetScriptSite
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScript_SetScriptSite"
ms.assetid: 47d94c32-09f8-4539-ac56-0236026f627b
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScript::SetScriptSite
스크립팅 엔진의 알립니다의 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) 호스트에서 제공 하는 인터페이스 사이트.  이 전에 다른이 메서드를 호출 [IActiveScript](../../winscript/reference/iactivescript.md) 인터페이스의 메서드를 사용 합니다.  
  
## 구문  
  
```  
HRESULT SetScriptSite(  
    IActiveScriptSite *pScriptSite  // address of host script site  
);  
```  
  
#### 매개 변수  
 `pScriptSite`  
 \[in\] 스크립팅 엔진의이 인스턴스에 연결 될 스크립트 호스트 제공 사이트의 주소입니다.  사이트는이 스크립트 엔진 인스턴스를 고유 하 게 할당 되어야 합니다. 다른 스크립팅 엔진을 공유할 수 없습니다.  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|성공|  
|`E_FAIL`|알 수 없는 오류가 발생 했습니다. 스크립팅 엔진 사이트 초기화를 완료 하지 못했습니다.|  
|`E_INVALIDARG`|인수가 잘못된 경우.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_UNEXPECTED`|호출이 필요 없습니다 \(예를 들어, 사이트는 이미 설정 된\).|  
  
## 참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)