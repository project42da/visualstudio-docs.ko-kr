---
title: "IDebugProperty::GetParent | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugProperty.GetParent
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IDebugProperty::GetParent"
ms.assetid: 673d625b-acca-45c4-88f4-b72275042f8f
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugProperty::GetParent
Parent 속성을의 속성을 가져옵니다.  
  
## 구문  
  
```  
HRESULT GetParent (  
   IDebugProperty** ppParent  
);  
```  
  
#### 매개 변수  
 `ppParent`  
 \[out\] 반환 된 `IDebugProperty` 인터페이스 속성의 부모를 나타냅니다.  
  
## 반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`.  
  
## 참고 항목  
 [IDebugProperty 인터페이스](../../winscript/reference/idebugproperty-interface.md)