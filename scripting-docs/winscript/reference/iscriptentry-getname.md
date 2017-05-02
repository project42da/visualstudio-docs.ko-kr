---
title: "IScriptEntry::GetName | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IScriptEntry.GetName
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IScriptEntry::GetName"
ms.assetid: 56daa288-618f-497c-a360-7d443afd478b
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# IScriptEntry::GetName
에 대 한 항목 \(예: 함수\)는 단일 개체를 나타내는 개체의 이름을 반환 합니다.  
  
## 구문  
  
```  
HRESULT GetName(  
   BSTR               *pbstr  
);  
```  
  
#### 매개 변수  
 `pbstr`  
 \[out\] 표시 되는 개체의 이름에 `IScriptEntry` 스크립트 블록.  항목이 단일 개체를 나타내지 않으면 NULL이 반환 됩니다.  
  
 자식 항목 단일 함수 개체를 나타냅니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)   
 [IScriptNode:: CreateChildEntry](../../winscript/reference/iscriptnode-createchildentry.md)