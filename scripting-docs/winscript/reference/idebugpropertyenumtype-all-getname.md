---
title: "IDebugPropertyEnumType_All::GetName | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugPropertyEnumType_All.GetName
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IDebugPropertyEnumType_All::GetName"
ms.assetid: 24bbe4d5-4263-48d0-8e8d-bff957ffcad2
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugPropertyEnumType_All::GetName
이름이 포함 된 BSTR 반환 된 `EnumType`.  
  
## 구문  
  
```  
HRESULT GetName(  
   BSTR*  pname  
);  
```  
  
#### 매개 변수  
 `pname`  
 \[out\] 이름을 포함 하는 BSTR에 `EnumType`.  
  
## 반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`.  
  
## 참고 항목  
 [IDebugPropertyEnumType\_All 인터페이스](../../winscript/reference/idebugpropertyenumtype-all-interface.md)