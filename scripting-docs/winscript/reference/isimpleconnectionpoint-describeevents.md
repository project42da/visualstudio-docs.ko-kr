---
title: "ISimpleConnectionPoint::DescribeEvents | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: ISimpleConnectionPoint.DescribeEvents
apilocation: pdm.dll
helpviewer_keywords: 
  - "ISimpleConnectionPoint::DescribeEvents"
ms.assetid: 659ea05f-d41e-424a-bb38-df7672b2d135
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# ISimpleConnectionPoint::DescribeEvents
각 이벤트에 대 한 이름과 dispid가 이벤트에 지정 된 범위를 반환합니다.  
  
## 구문  
  
```  
HRESULT DescribeEvents(  
   ULONG    iEvent,  
   ULONG    cEvents,  
   DISPID*  prgid,  
   BSTR*    prgbstr,  
   ULONG*   pcEventsFetched  
);  
```  
  
#### 매개 변수  
 `iEvent`  
 \[in\] 검색할 첫 번째 이벤트의 인덱스입니다.  
  
 `cEvents`  
 \[in\] 검색할 이벤트 수입니다.  
  
 `prgid`  
 \[out\] 이벤트의 DISPID 값의 배열입니다.  
  
 `prgbstr`  
 \[out\] 이벤트 이름의 배열입니다.  
  
 `pcEventsFetched`  
 \[out\] 실제 반입 된 이벤트 개수입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`S_FALSE`|사용할 수 있는 보다 자세한 이벤트를 요청 했습니다.  사용할 수 없는 이벤트 DISPID\_NULL 및 BSTR null로 표시 됩니다.|  
|`E_INVALIDARG`|요소를 가져오지 못했습니다.|  
  
## 설명  
 이 메서드는 이벤트의 지정 된 범위에서 각 이벤트에 대 한 이름과 DISPID 반환합니다.  
  
## 참고 항목  
 [ISimpleConnectionPoint 인터페이스](../../winscript/reference/isimpleconnectionpoint-interface.md)