---
title: IDebugFirewallConfigurationCallback2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugFirewallConfigurationCallback2 interface
ms.assetid: 0827361c-b97c-4851-9898-ab6d88c81811
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ab632bc7db06f01c6a88070a065c6939e4dbb91f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugfirewallconfigurationcallback2"></a>IDebugFirewallConfigurationCallback2
DCOM을 사용 하 여 요청 하는 디버그 엔진을 사용 하도록 설정 된 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] UI를 방화벽이 원격 디버깅을 차단 하지 것입니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugFirewallConfigurationCallback2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 세션 관리자의 포트 개체에 의해 구현 됩니다.  
  
## <a name="methods"></a>메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugFirewallConfigurationCallback2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[EnsureDCOMUnblocked](../../../extensibility/debugger/reference/idebugfirewallconfigurationcallback2-ensuredcomunblocked.md)|방화벽으로 차단 되지 원격 디버깅을 요청 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll