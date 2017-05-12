---
title: "IMachineDebugManagerCookie 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IMachineDebugManagerCookie 인터페이스"
ms.assetid: 04770935-3ccf-41e9-b0c1-c78376ab1e3c
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IMachineDebugManagerCookie 인터페이스
유사한는 `IMachineDebugManager` 인터페이스는 `IMachineDebugManagerCookie` 인터페이스를 지 원하는 디버그 쿠키.  
  
 이 인터페이스 \(함께 있는 `IDebugCookie` 인터페이스\) 스크립트 디버거가 해당 스크립트의 추적 것 없이 스크립트 디버거가 프로세스의 실행을 허용 합니다.  
  
 스크립트 디버거를 호출 하 여 `IDebugCookie::SetDebugCookie` 방법에는 프로세스 디버그 관리자 \(PDM\).  그런 다음 메서드를 사용 하 여이 추가 또는 제거 하거나에서 컴퓨터 디버그 관리자 \(MDM\), 스크립트 응용 프로그램에는 요청과 함께이 쿠키에서 PDM 보냅니다의 `IMachineDebugManagerCookie` 인터페이스.  다음은 MDM 변경 해당 쿠키에가 하는 것을 제외 하 고 모든 디버거를 알립니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IMachineDebugManagerCookie` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IMachineDebugManagerCookie::AddApplication](../../winscript/reference/imachinedebugmanagercookie-addapplication.md)|추가 응용 프로그램을 실행 하는 응용 프로그램 목록입니다.|  
|[IMachineDebugManagerCookie::EnumApplications](../../winscript/reference/imachinedebugmanagercookie-enumapplications.md)|현재 실행 중인 응용 프로그램 목록에 대 한 열거자를 반환 합니다.|  
|[IMachineDebugManagerCookie::RemoveApplication](../../winscript/reference/imachinedebugmanagercookie-removeapplication.md)|응용 프로그램 실행에서 제거 응용 프로그램 목록입니다.|  
  
## 참고 항목  
 [IMachineDebugManager 인터페이스](../../winscript/reference/imachinedebugmanager-interface.md)   
 [IDebugCookie 인터페이스](../../winscript/reference/idebugcookie-interface.md)