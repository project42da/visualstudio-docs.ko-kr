---
title: "IPerPropertyBrowsing2 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IPerPropertyBrowsing2
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IPerPropertyBrowsing2 인터페이스"
ms.assetid: 1e50b3f7-cc1c-495a-93c7-3ee03aea0b8a
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IPerPropertyBrowsing2 인터페이스
액세스 정보 속성 페이지에서 개체에서 제공 합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|`GetDisplayString`|지정 된 속성을 설명 하는 텍스트 문자열을 반환 합니다.|  
|`MapPropertyToPage`|지정 된 속성을 조작할 수 있는 속성 페이지의 CLSID를 반환 합니다.|  
|`GetPredefinedStrings`|카운트는 문자열 배열을 반환 \(`LPOLESTR` 포인터\) 지정 된 속성을 사용할 수 있는 허용 가능한 값에 대 한 설명을 나열 합니다.|  
|`SetPredefinedValue`|속성의 값을 토큰으로 식별 되는 미리 정의 된 값 설정`dwCookie.`|  
  
## 요구 사항  
 헤더: dbgprop.h