---
title: "IRemoteDebugApplication::ResumeFromBreakPoint | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IRemoteDebugApplication.ResumeFromBreakPoint
apilocation: pdm.dll
helpviewer_keywords: 
  - "IRemoteDebugApplication::ResumeFromBreakPoint"
ms.assetid: a613cc2b-1d69-4713-a235-64372c253b4a
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IRemoteDebugApplication::ResumeFromBreakPoint
중단점에는 현재 응용 프로그램을 계속 합니다.  
  
## 구문  
  
```  
HRESULT ResumeFromBreakPoint(  
   IRemoteDebugApplicationThread*  prptFocus,  
   BREAKRESUMEACTION               bra,  
   ERRORRESUMEACTION               era  
);  
```  
  
#### 매개 변수  
 `prptFocus`  
 \[in\] 모드, 단계별 실행 모드에 의해 영향을 받을 수는 스레드 단계별로 실행 합니다.  
  
 `bra`  
 \[in\] 응용 프로그램을 다시 시작 시 수행할 작업입니다.  
  
 `era`  
 \[in\] 오류가 발생 하 여 응용 프로그램을 중지 한 경우에서 수행할 동작입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 현재 중단점에서 응용 프로그램을 계속 합니다.  
  
## 참고 항목  
 [IRemoteDebugApplication 인터페이스](../../winscript/reference/iremotedebugapplication-interface.md)   
 [BREAKRESUMEACTION 열거형](../../winscript/reference/breakresumeaction-enumeration.md)   
 [ERRORRESUMEACTION 열거형](../../winscript/reference/errorresumeaction-enumeration.md)