---
title: "IRemoteDebugApplicationEx 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IRemoteDebugApplicationEx 인터페이스"
ms.assetid: 8e16164d-dbb2-4488-9507-25ae34f343dc
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# IRemoteDebugApplicationEx 인터페이스
실행 중인 응용 프로그램을 나타냅니다.  운영 체제 프로세스에 일치 하지 않아도 됩니다.  일반적으로 디버거에서 디버깅을 위한 응용 프로그램을 대상 으로합니다.  일반적으로 프로세스 디버그 관리자 응용 프로그램 개체를 구현 합니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IRemoteDebugApplicationEx` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IRemoteDebugApplicationEx:GetHostPid](../../winscript/reference/iremotedebugapplicationex-gethostpid.md)|호스트 응용 프로그램의 프로세스 ID를 반환합니다.|  
|GetHostMachineName|호스트 응용 프로그램을 실행 하는 컴퓨터의 이름을 반환 합니다.|  
|[IRemoteDebugApplicationEx:SetLocale](../../winscript/reference/iremotedebugapplicationex-setlocale.md)|디버거 지역화 된 언어를 설정합니다.|  
|[IRemoteDebugApplicationEx:ForceStepMode](../../winscript/reference/iremotedebugapplicationex-forcestepmode.md)|디버거를 한 단계씩 실행 모드를 강제합니다.|  
|[IRemoteDebugApplicationEx:RevokeBreak](../../winscript/reference/iremotedebugapplicationex-revokebreak.md)|Break 명령을 취소합니다.|  
|SetProxyBlanketAndAddRef|프록시에서 원격 Windows 95 기반 운영 체제에서 디버깅 호환 되도록 디버거 개체에 대 한 COM 보안 정보를 업데이트 합니다.|  
|ReleaseFromSetProxyBlanket|Setproxyblanketandaddref에서 Addref를 릴리스 합니다.|