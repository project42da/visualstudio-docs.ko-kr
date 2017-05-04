---
title: "IPerPropertyBrowsing2::GetPredefinedStrings | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IPerPropertyBrowsing2.GetPredefinedStrings
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IPerPropertyBrowsing2::GetPredefinedStrings"
ms.assetid: d2fa30f7-a566-4dbd-8b47-ffdc00419771
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IPerPropertyBrowsing2::GetPredefinedStrings
호출자가 계산에이 속성 값을 나타내는 문자열 포인터 배열이 목록 상자를 채울 수 있습니다.  
  
## 구문  
  
```  
HRESULT GetPredefinedStrings(  
   DISPID  dispid,  
   CALPOLESTR*  pCaStrings,  
   CADWORD*  pCaCookies  
);  
```  
  
#### 매개 변수  
 `dispid`  
 \[in\] 호출자에 게 문자열 목록 요청 속성의 디스패치 식별자입니다.  
  
 `pCaStrings`  
 \[out\] 요소 개수 및 메서드가 할당 된 배열의 문자열 포인터의 주소를 포함 한 호출자 할당, 배열 구조에 대 한 포인터입니다.  메서드가 실패 하면 메모리가 할당 되지 않습니다, 및 구조의 내용이 정의 되지 않습니다.  
  
 `pCaCookies`  
 \[out\] 호출자가 할당 한 포인터 요소 개수 및 주소 Dword 배열 할당 메서드를 포함 하는 배열 구조를 계산 합니다.  메서드가 실패 하면 메모리가 할당 되지 않습니다, 및 구조의 내용이 정의 되지 않습니다.  
  
## 반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`.  
  
## 참고 항목  
 [IPerPropertyBrowsing2 인터페이스](../../winscript/reference/iperpropertybrowsing2-interface-1.md)