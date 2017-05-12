---
title: "IPerPropertyBrowsing2::SetPredefinedValue | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IPerPropertyBrowsing2.SetPredefinedValue
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IPerPropertyBrowsing2::SetPredefinedValue"
ms.assetid: 3aff5300-c5a4-4d9b-9d47-a75b64014ac4
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IPerPropertyBrowsing2::SetPredefinedValue
지정 된 속성 값을 설정 하는 `dispID`.  미리 정의 된 값은 토큰으로 식별 되는`dwCookie.`  
  
## 구문  
  
```  
HRESULT SetPredefinedValue(  
   DISPID  dispid,  
   DWORD  dwCookie  
);  
```  
  
#### 매개 변수  
 `dispid`  
 \[in\] 미리 정의 된 값이 설정 되는 속성의 디스패치 식별자입니다.  
  
 `dwCookie`  
 \[in\] 설정할 값을 식별 하는 토큰입니다.  
  
## 반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`.  
  
## 참고 항목  
 [IPerPropertyBrowsing2 인터페이스](../../winscript/reference/iperpropertybrowsing2-interface-1.md)