---
title: "IPerPropertyBrowsing2::GetDisplayString | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IPerPropertyBrowsing2.GetDisplayString
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IPerPropertyBrowsing2::GetDisplayString"
ms.assetid: 8f75c6a9-86a9-4e2d-8cb4-74e7b1c0a524
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IPerPropertyBrowsing2::GetDisplayString
가져옵니다 반환 되는 텍스트는 기본적으로 볼 수 없는 형식을 표시 하는 문자열 속성을 설명 하는 이름 이므로 호출자의 사용자 인터페이스에 표시 될 수 있습니다.  
  
## 구문  
  
```  
HRESULT GetDisplayString(  
   DISPID  dispid,  
   BSTR*  pBstr  
);  
```  
  
#### 매개 변수  
 `dispid`  
 \[in\] 표시 이름이 요청 된 속성의 식별자를 발송 합니다.  
  
 `pBstr`  
 \[out\] 포인터는 `BSTR` 로 식별 되는 속성의 표시 이름이 포함 된 `dispID`.  
  
## 반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`.  
  
## 설명  
 반환 된 문자열이 속성 값이 잘못 되었습니다.  이 속성의 문자열 표시만 됩니다.  
  
## 참고 항목  
 [IPerPropertyBrowsing2 인터페이스](../../winscript/reference/iperpropertybrowsing2-interface-1.md)