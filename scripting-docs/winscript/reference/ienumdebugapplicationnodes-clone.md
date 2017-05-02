---
title: "IEnumDebugApplicationNodes::Clone | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IEnumDebugApplicationNodes.Clone
apilocation: pdm.dll
helpviewer_keywords: 
  - "IEnumDebugApplicationNodes::Clone"
ms.assetid: 7190954d-e2da-4a84-8e37-81d4d27886a8
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IEnumDebugApplicationNodes::Clone
현재 열거자와 상태가 같은 열거자를 만듭니다.  
  
## 구문  
  
```  
HRESULT Clone(  
   IEnumDebugApplicationNodes**  pperddp  
);  
```  
  
#### 매개 변수  
 `pperddp`  
 \[out\] 반환 된 `IEnumDebugApplicationNodes` 인터페이스의 열거자의 클론.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 현재 열거자와 같은 상태를 포함 하는 열거자를 만듭니다.  
  
## 참고 항목  
 [IEnumDebugApplicationNodes 인터페이스](../../winscript/reference/ienumdebugapplicationnodes-interface.md)