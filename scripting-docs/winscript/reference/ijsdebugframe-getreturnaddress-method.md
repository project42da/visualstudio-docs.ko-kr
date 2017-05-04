---
title: "IJsDebugFrame::GetReturnAddress 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJsDebugFrame.GetReturnAddress
apilocation: jscript9diag.dll
ms.assetid: 7f10c1d6-d7b9-402e-9020-04cded37f9d3
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugFrame::GetReturnAddress 메서드
프레임의 '시작'\(GetStackRange 참조\)에 푸시된 반송 주소를 가져옵니다.  
  
## 구문  
  
```  
HRESULT GetReturnAddress(  
   UINT64 *pReturnAddress  
);  
```  
  
#### 매개 변수  
 `pReturnAddress`  
 \[out\] 반환 주소입니다.  
  
## 반환 값  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebugFrame 인터페이스](../../winscript/reference/ijsdebugframe-interface.md)