---
title: "IScriptEntry::SetItemName | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IScriptEntry.SetItemName
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IScriptEntry::SetItemName"
ms.assetid: 9551a7ec-38f8-466a-9722-09367763f380
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# IScriptEntry::SetItemName
식별 항목 이름을 설정 하는 `IScriptEntry` 개체입니다.  
  
## 구문  
  
```  
HRESULT SetItemName(  
   LPCOLESTR          psz  
);  
```  
  
#### 매개 변수  
 `psz`  
 \[in\] 항목 이름이 포함 된 버퍼의 주소입니다.  항목 이름 항목을 식별 하는 호스트에서 사용 됩니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_FAIL`|메서드가 실패 했습니다.|  
  
## 설명  
 에 대 한 `IScriptEntry` 개체에서이 메서드는 반환 `S_OK`.  
  
 에 대 한 `IScriptScriptlet` 개체 \(파생에서 `IScriptEntry`\),이 메서드를 반환 합니다. `E_FAIL`.  에 대 한 `IScriptScriptlet` 개체에서 항목 이름으로 설정 되어 [IActiveScriptAuthor::AddScriptlet](../../winscript/reference/iactivescriptauthor-addscriptlet.md) 및 변경할 수 없습니다.  
  
## 참고 항목  
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)   
 [IScriptEntry::GetItemName](../../winscript/reference/iscriptentry-getitemname.md)