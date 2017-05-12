---
title: "IJsDebugProcess 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: a7ad5525-55b7-4c68-a4f7-c508f7877712
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# IJsDebugProcess 인터페이스
대상 프로세스를 검사하고 제어하기 위한 루틴을 제공합니다.  
  
## 구문  
  
```  
IJsDebugProcess : public IUnknown;  
```  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[IJsDebugProcess::CreateBreakPoint 메서드](../../winscript/reference/ijsdebugprocess-createbreakpoint-method.md)|문서의 지정된 위치에 중단점을 설정합니다.|  
|[IJsDebugProcess::CreateStackWalker 메서드](../../winscript/reference/ijsdebugprocess-createstackwalker-method.md)|스택 워커에 대한 팩터리 메서드입니다.|  
|[IJsDebugProcess::PerformAsyncBreak 메서드](../../winscript/reference/ijsdebugprocess-performasyncbreak-method.md)|중단 모드에서 스크립트 엔진은 다음 스크립트 명령을 중단하기 위해 배치합니다.|  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [Windows 스크립트 인터페이스 참조](../../winscript/reference/windows-script-interfaces-reference.md)