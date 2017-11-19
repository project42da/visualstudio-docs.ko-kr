---
title: "IDebugSessionProviderEx 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 26c5da2d-8c93-4d2b-94d2-97aaa377dcfe
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 545b60f13e86e59143ce0e57f454b13f61041f11
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugsessionproviderex-interface"></a>IDebugSessionProviderEx 인터페이스
디버거가 디버깅 호스트 및 언어에서 시작을 사용 하려면 IDE에서 제공 하는 기본 인터페이스입니다. 실행 중인 응용 프로그램에 대 한 디버그 세션을 설정 합니다. 이 인터페이스는 컴퓨터 디버그 관리자에 의해 구현 됩니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IDebugSessionProviderEx` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugSessionProviderEx:CanJITDebug](../../winscript/reference/idebugsessionproviderex-canjitdebug.md)|Just In Time 디버깅은 지정된 된 응용 프로그램으로 이전에 가능 여부를 결정 합니다.|  
|[IDebugSessionProviderEx:StartDebugSession](../../winscript/reference/idebugsessionproviderex-startdebugsession.md)|지정한 응용 프로그램에서 디버그 세션을 시작합니다.|