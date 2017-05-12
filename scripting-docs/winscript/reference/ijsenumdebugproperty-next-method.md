---
title: "IJsEnumDebugProperty::Next 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJsEnumDebugProperty.Next
apilocation: jscript9diag.dll
ms.assetid: 9fad1893-483a-440c-88c1-469494212300
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsEnumDebugProperty::Next 메서드
이 개체의 속성을 읽습니다.  
  
## 구문  
  
```  
HRESULT Next(  
   ULONG count,  
   IJsDebugProperty **ppDebugProperty,  
   ULONG *pActualCount  
);  
```  
  
#### 매개 변수  
 `count`  
 \[in\] 읽을 속성 수입니다.  
  
 `ppDebugProperty`  
 \[out\] 속성 브라우저를 나타내는 개체입니다.  
  
 `pActualCount`  
 \[out\] 개체의 실제 속성 수입니다.  
  
## 반환 값  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsEnumDebugProperty 인터페이스](../../winscript/reference/ijsenumdebugproperty-interface.md)