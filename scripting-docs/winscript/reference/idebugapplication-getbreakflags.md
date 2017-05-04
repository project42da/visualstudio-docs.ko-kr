---
title: "IDebugApplication::GetBreakFlags | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugApplication.GetBreakFlags
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugApplication::GetBreakFlags"
ms.assetid: 0532ba94-f791-46ad-88ae-5f6ba220b667
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplication::GetBreakFlags
응용 프로그램에 대 한 현재 중단 플래그를 반환합니다.  
  
## 구문  
  
```  
HRESULT GetBreakFlags(  
   APPBREAKFLAGS*                   pabf,  
   IRemoteDebugApplicationThread**  pprdatSteppingThread  
);  
```  
  
#### 매개 변수  
 `pabf`  
 \[out\] 응용 프로그램에 대 한 현재 중단 플래그입니다.  
  
 `pprdatSteppingThread`  
 \[out\] 현재 실행 중인 스레드입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 현재 중단 플래그는 응용 프로그램에 반환합니다.  
  
## 참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)   
 [APPBREAKFLAGS 열거형](../../winscript/reference/appbreakflags-enumeration.md)