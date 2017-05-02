---
title: "IScriptScriptlet::SetSubItemName | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IScriptScriptlet.SetSubItemName
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IScriptScriptlet::SetSubItemName"
ms.assetid: 619f222f-b4c3-4c7b-9d19-e4e7037343a6
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IScriptScriptlet::SetSubItemName
마지막 식별자는 스크립트릿 개체 호스트의 정규화 된 이름을 설정합니다.  
  
## 구문  
  
```  
HRESULT SetSubItemName(  
   LPCOLESTR          psz  
);  
```  
  
#### 매개 변수  
 `psz`  
 정규화 된 호스트의 이름을 스크립트릿 수준이 둘 이상인 경우 `psz` 두 번째 수준 식별자는 버퍼 주소입니다.  
  
 정규화 된 호스트의 경우 스크립트릿 한 수준 이름이 `psz` 의 첫 번째 수준 식별자는 버퍼 주소입니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 [IScriptScriptlet 인터페이스](../../winscript/reference/iscriptscriptlet-interface.md)