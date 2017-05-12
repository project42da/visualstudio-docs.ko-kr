---
title: "IActiveScriptAuthor::RemoveNamedItem | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptAuthor.RemoveNamedItem
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptAuthor::RemoveNamedItem"
ms.assetid: 1173ef46-39a5-4bc1-8e0c-89259a16be16
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# IActiveScriptAuthor::RemoveNamedItem
제거는 `NamedItem` 개체에서 네임 스페이스를 스크립트 엔진을 제작 합니다.  
  
## 구문  
  
```  
HRESULT RemoveNamedItem(  
   LPCOLESTR          pszName  
);  
```  
  
#### 매개 변수  
 `pszName`  
 \[in\] 식별 하는 버퍼의 주소는 `NamedItem` 개체를 제거 합니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`S_FALSE`|`NamedItem` 개체는 스크립트 엔진 제작의 네임 스페이스에 표시 되지 않습니다.|  
  
## 설명  
 [IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md)주입 하는 데 사용 되는 `NamedItem` 개체로 스크립트 엔진의 네임 스페이스를 제작 합니다.  
  
## 참고 항목  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)   
 [IActiveScriptAuthor::AddNamedItem](../../winscript/reference/iactivescriptauthor-addnameditem.md)