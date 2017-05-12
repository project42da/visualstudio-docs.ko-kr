---
title: "IObjectIdentity::IsEqualObject | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IObjectIdentity.IsEqualObject
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IsEqualObject 메서드"
ms.assetid: 78c5c5c2-d299-4036-986c-7c1d87cbe7cd
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IObjectIdentity::IsEqualObject
개체와 현재 개체가 같은지 확인 합니다.  
  
## 구문  
  
```  
HRESULT IsEqualObject(  
  IUnknown*  punk  
);  
```  
  
#### 매개 변수  
 `punk`  
 \[in\] 현재 개체와 비교할 개체의 주소입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|개체는 같습니다.|  
|`S_FALSE`|개체가 같지 않습니다.|  
  
## 설명  
 구현에 `IsEqualObject` 메서드 반환 `S_OK` 개체는 동일한 경우에.  
  
## 참고 항목  
 [IObjectIdentity 인터페이스](../../winscript/reference/iobjectidentity-interface.md)