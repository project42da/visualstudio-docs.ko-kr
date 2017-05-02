---
title: "IEnumDebugExpressionContexts::Clone | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IEnumDebugExpressionContexts.Clone
apilocation: jscript.dll
helpviewer_keywords: 
  - "IEnumDebugExpressionContexts::Clone"
ms.assetid: c8070ae1-120c-4b5d-bd3d-ae8fca6f9277
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IEnumDebugExpressionContexts::Clone
현재 열거자와 상태가 같은 열거자를 만듭니다.  
  
## 구문  
  
```  
HRESULT Clone(  
   IEnumDebugExpressionContexts**  ppedec  
);  
```  
  
#### 매개 변수  
 `ppedec`  
 \[out\] 반환 된 `IEnumDebugExpressionContexts` 인터페이스의 열거자의 클론.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 현재 열거자와 같은 상태를 포함 하는 열거자를 만듭니다.  
  
## 참고 항목  
 [IEnumDebugExpressionContexts 인터페이스](../../winscript/reference/ienumdebugexpressioncontexts-interface.md)