---
title: "IDebugFirewallConfigurationCallback2 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugFirewallConfigurationCallback2 인터페이스"
ms.assetid: 0827361c-b97c-4851-9898-ab6d88c81811
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugFirewallConfigurationCallback2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

DCOM 요청 하는 데 사용 되는 디버그 엔진 수는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 방화벽 원격 디버깅이 차단 합니다 있는지 확인 하는 사용자 인터페이스입니다.  
  
## 구문  
  
```  
IDebugFirewallConfigurationCallback2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 세션 관리자의 포트 개체에 의해 구현 됩니다.  
  
## 메서드  
 다음 표에서 메서드를 `IDebugFirewallConfigurationCallback2`.  
  
|메서드|설명|  
|---------|--------|  
|[EnsureDCOMUnblocked](../../../extensibility/debugger/reference/idebugfirewallconfigurationcallback2-ensuredcomunblocked.md)|방화벽이 원격 디버깅 차단 되지 것을 요청 합니다.|  
  
## 요구 사항  
 헤더: Msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll