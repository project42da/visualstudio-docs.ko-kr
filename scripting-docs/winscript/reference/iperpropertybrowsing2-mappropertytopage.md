---
title: "IPerPropertyBrowsing2::MapPropertyToPage | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IPerPropertyBrowsing2.MapPropertyToPage
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IPerPropertyBrowsing2::MapPropertyToPage"
ms.assetid: e6418a8e-500b-42e1-9b5a-52e6f7567f99
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IPerPropertyBrowsing2::MapPropertyToPage
이 속성을 편집 하는 데 사용할 수 있는 속성 페이지의 CLSID를 반환 합니다.  
  
## 구문  
  
```  
HRESULT MapPropertyToPage(  
   DISPID  dispid,  
   CLSID*  pClsidPropPage  
);  
```  
  
#### 매개 변수  
 `dispid`  
 \[in\] 원하는 속성의 식별자를 발송 합니다.  
  
 `pClsidPropPage`  
 \[out\] 속성과 관련 된 속성 페이지를 식별 하는 CLSID에 대 한 포인터입니다.  이 메서드는 실패 하는 경우 \*`pClsidPropPage` CLSID\_NULL에 설정 됩니다.  
  
## 반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`.  
  
## 참고 항목  
 [IPerPropertyBrowsing2 인터페이스](../../winscript/reference/iperpropertybrowsing2-interface-1.md)