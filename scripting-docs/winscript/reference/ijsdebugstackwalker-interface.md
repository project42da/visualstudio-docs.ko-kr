---
title: "IJsDebugStackWalker 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 3fe30394-49c8-48e9-bde9-ffe5d79b2121
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugStackWalker 인터페이스
지정된 스레드의 스택 워커를 나타냅니다.  
  
## 구문  
  
```  
IJsDebugStackWalker : public IUnknown;  
```  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[IJsDebugStackWalker::GetNext 메서드](../../winscript/reference/ijsdebugstackwalker-getnext-method.md)|다음 프레임을 가져옵니다.|  
  
## 설명  
 스택 워커는 대상이 정지되어 있는 동안에만 만들 수 있으며 대상 프로세스가 다시 계속된 후에 잘못됩니다.  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [Windows 스크립트 인터페이스 참조](../../winscript/reference/windows-script-interfaces-reference.md)