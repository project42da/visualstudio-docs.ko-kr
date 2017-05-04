---
title: "IScriptEntry::GetItemName | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IScriptEntry.GetItemName
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IScriptEntry::GetItemName"
ms.assetid: 8f2562f1-8231-4a39-ad79-074f9ec3d403
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IScriptEntry::GetItemName
식별 항목 이름을 반환 하는 `IScriptEntry` 개체입니다.  
  
## 구문  
  
```  
HRESULT GetItemName(  
   BSTR               *pbstr  
);  
```  
  
#### 매개 변수  
 `pbstr`  
 \[out\] 항목 이름이 포함 된 버퍼의 주소입니다.  항목 이름 항목을 식별 하는 호스트에서 사용 됩니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 에 대 한 `IScriptScriptlet` 개체를 사용 하 여 항목 이름을 설정할 [IActiveScriptAuthor::AddScriptlet](../../winscript/reference/iactivescriptauthor-addscriptlet.md).  다른 인터페이스에 대 한 항목 이름을 사용 하 여 설정 [IScriptEntry::SetItemName](../../winscript/reference/iscriptentry-setitemname.md).  
  
## 참고 항목  
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)