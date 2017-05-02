---
title: "IDispatchEx::GetNameSpaceParent | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDispatchEx.GetNameSpaceParent
apilocation: scrobj.dll
helpviewer_keywords: 
  - "GetNameSpaceParent 메서드"
ms.assetid: 0b077d39-2fd6-4390-8cd5-128d9b8dc90c
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDispatchEx::GetNameSpaceParent
인터페이스는 개체의 부모 네임 스페이스를 검색합니다.  
  
## 구문  
  
```  
HRESULT GetNameSpaceParent(  
   IUnknown **ppunk  
);  
```  
  
#### 매개 변수  
 `ppunk`  
 주소는 `IUnknown` 네임 스페이스의 상위 인터페이스를 수신 하는 인터페이스 포인터입니다.  
  
## 반환 값  
 반환 `S_OK` 성공 하는 경우 또는 다른 OLE 정의 된 오류 코드입니다.  
  
## 참고 항목  
 [IDispatchEx 인터페이스](../../winscript/reference/idispatchex-interface.md)