---
title: "IDebugSessionProviderEx 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 26c5da2d-8c93-4d2b-94d2-97aaa377dcfe
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# IDebugSessionProviderEx 인터페이스
IDE 호스트 언어 기반의 디버깅을 사용 하려면 디버거에 의해 제공 되는 기본 인터페이스입니다.  실행 중인 응용 프로그램에 대 한 디버그 세션을 설정합니다.  컴퓨터 디버그 관리자가이 인터페이스를 구현 합니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IDebugSessionProviderEx` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IDebugSessionProviderEx:CanJITDebug](../../winscript/reference/idebugsessionproviderex-canjitdebug.md)|Just In Time 디버깅 가능으로 지정 된 응용 프로그램 인지 여부를 결정 합니다.|  
|[IDebugSessionProviderEx:StartDebugSession](../../winscript/reference/idebugsessionproviderex-startdebugsession.md)|지정 된 응용 프로그램을 디버그 세션을 시작합니다.|