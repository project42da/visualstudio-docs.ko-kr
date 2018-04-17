---
title: IDebugNoSymbolsEvent2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugNoSymbolsEvent2 interface
ms.assetid: f6fb6388-47f6-4385-9ad5-95d62f9a7592
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bb7719ff66ac284d07da2ddfca25fe6898c93220
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugnosymbolsevent2"></a>IDebugNoSymbolsEvent2
신호는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 디버거는 기호를 찾을 수에서 시작 된 실행 파일에는 사용자에 게 경고 하는 UI입니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugNoSymbolsEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진에 의해 구현 및에서 소비 되는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 디버거 UI입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll