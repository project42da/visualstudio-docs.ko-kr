---
title: "IEnumJsStackFrames::Next 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IEnumJsStackFrames.Next
apilocation: jscript9diag.dll
ms.assetid: efceb3a1-9239-4f55-9cbb-94670679988b
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IEnumJsStackFrames::Next 메서드
지정된 프레임 수를 가져옵니다.  
  
## 구문  
  
```  
HRESULT Next(  
   ULONG cFrameCount,  
   JS_NATIVE_FRAME *pFrames,  
   ULONG *pcFetched  
);  
```  
  
#### 매개 변수  
 `cFrameCount`  
 \[in\] 가져올 프레임의 수입니다.  
  
 `pFrames`  
 \[out\] 프레임을 저장하는 배열입니다.  
  
 `pcFetched`  
 \[out\] 반환된 프레임 수입니다.  
  
## 반환 값  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IEnumJsStackFrames 인터페이스](../../winscript/reference/ienumjsstackframes-interface.md)