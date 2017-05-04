---
title: "ISimpleConnectionPoint::GetEventCount | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: ISimpleConnectionPoint.GetEventCount
apilocation: pdm.dll
helpviewer_keywords: 
  - "ISimpleConnectionPoint::GetEventCount"
ms.assetid: f1527d5b-6076-4536-8e59-e55da741ef39
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# ISimpleConnectionPoint::GetEventCount
이 인터페이스에서 노출 하는 이벤트의 수를 반환 합니다.  
  
## 구문  
  
```  
HRESULT GetEventCount(  
   ULONG*  pulCount  
);  
```  
  
#### 매개 변수  
 `pulCount`  
 \[out\] 이 인터페이스 개수에 노출 되는 이벤트 수입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는이 인터페이스를 노출 하는 이벤트 개수를 반환 합니다.  
  
## 참고 항목  
 [ISimpleConnectionPoint 인터페이스](../../winscript/reference/isimpleconnectionpoint-interface.md)