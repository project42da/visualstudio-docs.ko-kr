---
title: "IActiveScriptSiteDebugEx 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IActiveScriptSiteDebugEx Interface
ms.assetid: 76869378-1a7b-47bd-8cd0-acc31f91d58d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2cf5849ff1fca282bace97774c6b7ac9e4510226
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptsitedebugex-interface"></a>IActiveScriptSiteDebugEx 인터페이스
와 함께이 인터페이스를 구현에서 `IActiveScriptSiteDebug` 응용 프로그램에서 런타임 오류에 대 한 알림을 가져오고 필요에 따라 디버깅을 위해 응용 프로그램에 연결 하는 호스트를 작성 하는 경우 인터페이스입니다. 디버그 프로세스 관리자를 통해 알림을 제공 `IActiveScriptDebug` 컴퓨터에서 발견 되는 Just In Time 스크립트 디버거에 면 합니다. 없는 Just In Time 스크립트 디버거가 발견 된 PDM를 통해 알림을 제공 `IActiveScriptDebugEx` 대신 합니다.  
  
 런타임 오류에 대 한 알림을 가져오려면 호스트 처리 해야 [ActiveScriptSiteDebug::OnScriptErrorDebug](http://msdn.microsoft.com/en-us/cf7639f9-a699-4571-9f3a-82ef52c0b5f4)합니다. 사용자 작업에 따라, 다음 지 결정할 수 있습니다는 OnScriptErrorDebug에 디버거를 시작 반환 하거나 내부 디버거 및 수익을 연결 하려면 `pfEnterDebugger` 매개 변수입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IActiveScriptSiteDebugEx::OnCanNotJITScriptErrorDebug](../../winscript/reference/iactivescriptsitedebugex-oncannotjitscripterrordebug.md)|프로세스 관리자를 디버그할 때 스크립트 런타임 오류에 대 한 호스트 된 외부 Just In Time 디버거에 찾지 못하면에 알립니다.|