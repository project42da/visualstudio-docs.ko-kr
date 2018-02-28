---
title: "IMachineDebugManagerCookie 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IMachineDebugManagerCookie interface
ms.assetid: 04770935-3ccf-41e9-b0c1-c78376ab1e3c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a03b959a7eb09f3b85530bbba07d1d2dc7f8948a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="imachinedebugmanagercookie-interface"></a>IMachineDebugManagerCookie 인터페이스
비슷합니다는 `IMachineDebugManager` 인터페이스는 `IMachineDebugManagerCookie` 인터페이스에서 디버그 쿠키를 지원 합니다.  
  
 이 인터페이스 (함께 `IDebugCookie` 인터페이스) 디버거가 계속 이러한 스크립트는 추적 하지 않고도 스크립트 디버거 프로세스에서 실행 되도록 스크립트를 허용 합니다.  
  
 스크립트 디버거 호출는 `IDebugCookie::SetDebugCookie` 메서드 프로세스 디버깅 관리자 (PDM)에 있습니다. 그런 다음는 PDM이이 쿠키를 추가 하거나 또는에서 컴퓨터 디버그 관리자 (MDM), 스크립트 응용 프로그램을 제거할 모든 요청과 함께 사용 하 여 보냅니다의 메서드는 `IMachineDebugManagerCookie` 인터페이스입니다. 에 MDM에는 다음 내용이 해당 쿠키를 제외 하 고 변경 내용의 모든 디버거를 알립니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IMachineDebugManagerCookie` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IMachineDebugManagerCookie::AddApplication](../../winscript/reference/imachinedebugmanagercookie-addapplication.md)|응용 프로그램을 실행 하는 추가 하는 응용 프로그램 목록입니다.|  
|[IMachineDebugManagerCookie::EnumApplications](../../winscript/reference/imachinedebugmanagercookie-enumapplications.md)|실행 중인 응용 프로그램의 현재 목록의 열거자를 반환 합니다.|  
|[IMachineDebugManagerCookie::RemoveApplication](../../winscript/reference/imachinedebugmanagercookie-removeapplication.md)|실행 되는 응용 프로그램을 제거 응용 프로그램 목록입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [IMachineDebugManager 인터페이스](../../winscript/reference/imachinedebugmanager-interface.md)   
 [IDebugCookie 인터페이스](../../winscript/reference/idebugcookie-interface.md)