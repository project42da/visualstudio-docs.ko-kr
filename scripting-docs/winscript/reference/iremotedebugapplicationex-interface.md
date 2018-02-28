---
title: "IRemoteDebugApplicationEx 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IRemoteDebugApplicationEx Interface
ms.assetid: 8e16164d-dbb2-4488-9507-25ae34f343dc
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3360cea0d1649348a795356ad827b32b6f8ebc19
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iremotedebugapplicationex-interface"></a>IRemoteDebugApplicationEx 인터페이스
실행 중인 응용 프로그램을 나타냅니다. 운영 체제 프로세스에 맞게 필요는 없습니다. 일반적으로 디버거는 디버깅을 위해 응용 프로그램을 대상 으로합니다. 디버그 프로세스 관리자는 일반적으로 응용 프로그램 개체를 구현합니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IRemoteDebugApplicationEx` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IRemoteDebugApplicationEx:GetHostPid](../../winscript/reference/iremotedebugapplicationex-gethostpid.md)|호스트 응용 프로그램에 대 한 프로세스 ID를 반환합니다.|  
|GetHostMachineName|호스트 응용 프로그램에서 실행 되는 컴퓨터의 이름을 반환 합니다.|  
|[IRemoteDebugApplicationEx:SetLocale](../../winscript/reference/iremotedebugapplicationex-setlocale.md)|디버거 지역화에 대 한 언어를 설정합니다.|  
|[IRemoteDebugApplicationEx:ForceStepMode](../../winscript/reference/iremotedebugapplicationex-forcestepmode.md)|단일 단계 모드에 디버거를 강제로 수행합니다.|  
|[IRemoteDebugApplicationEx:RevokeBreak](../../winscript/reference/iremotedebugapplicationex-revokebreak.md)|Break 명령을 취소합니다.|  
|SetProxyBlanketAndAddRef|Windows 95 기반 운영 체제에서 원격 디버깅와 호환성을 위해 디버거 개체에 대 한 프록시에 COM 보안 정보를 업데이트 합니다.|  
|ReleaseFromSetProxyBlanket|SetProxyBlanketAndAddRef에서 AddRef를 릴리스 합니다.|