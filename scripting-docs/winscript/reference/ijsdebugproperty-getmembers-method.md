---
title: "IJsDebugProperty::GetMembers 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJsDebugProperty.GetMembers
apilocation: jscript9diag.dll
ms.assetid: a32b5372-d9cb-4b9a-9bc2-81b5e1df365c
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugProperty::GetMembers 메서드
이 개체의 멤버를 가져옵니다.  
  
## 구문  
  
```  
HRESULT GetMembers(  
   JS_PROPERTY_MEMBERS members,  
   IJsEnumDebugProperty **ppEnum  
);  
```  
  
#### 매개 변수  
 `members`  
 \[in\] 멤버 정보에 포함된 것을 지정하는 플래그입니다.  
  
 `ppEnum`  
 \[out\] 개체의 멤버입니다.  
  
## 반환 값  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebugProperty 인터페이스](../../winscript/reference/ijsdebugproperty-interface.md)