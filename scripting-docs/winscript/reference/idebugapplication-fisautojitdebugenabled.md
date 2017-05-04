---
title: "IDebugApplication::FIsAutoJitDebugEnabled | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugApplication.FIsAutoJitDebugEnabled
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugApplication::FIsAutoJitDebugEnabled"
ms.assetid: 0551dd3b-e6eb-442a-8201-418f96fe62df
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplication::FIsAutoJitDebugEnabled
Just in time \(JIT\) 디버거 자동 디버그 단순 호스트에 등록 되어 있는지 확인 합니다.  
  
## 구문  
  
```  
BOOL FIsAutoJitDebugEnabled();  
```  
  
#### 매개 변수  
 이 메서드는 매개 변수를 사용하지 않습니다.  
  
## 반환 값  
 메서드가 성공 및 JIT 디버거가 디버그 자동 단순 호스트에 등록 된 메서드를 반환 합니다. `TRUE`.  그렇지 않으면 `FALSE`가 반환됩니다.  
  
## 설명  
 JIT 디버거 자동 디버그 단순 호스트에 등록 되어 있는 경우이 메서드를 결정 합니다.  
  
## 참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)