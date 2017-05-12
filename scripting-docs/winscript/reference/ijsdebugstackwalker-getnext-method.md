---
title: "IJsDebugStackWalker::GetNext 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJsDebugStackWalker.GetNext
apilocation: jscript9diag.dll
ms.assetid: 0b124768-50d3-4a69-876c-1aa337839a4e
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugStackWalker::GetNext 메서드
다음 프레임을 가져옵니다.  
  
## 구문  
  
```  
HRESULT GetNext(  
   IJsDebugFrame **ppFrame  
);  
```  
  
#### 매개 변수  
 `ppFrame`  
 \[out\] 스택 프레임을 나타내는 개체입니다.  
  
## 반환 값  
  
## 설명  
 열거할 자세한 스택 프레임이 없는 경우 E\_JsDEBUG\_OUTSIDE\_OF\_VM를 반환합니다.  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebugStackWalker 인터페이스](../../winscript/reference/ijsdebugstackwalker-interface.md)