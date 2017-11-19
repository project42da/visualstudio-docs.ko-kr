---
title: IDebugDynamicFieldCOMPlus | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugDynamicFieldCOMPlus interface
ms.assetid: c3a25f27-327a-4bdb-b026-27d436ddcd0c
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 40bd08ef1cba620332d613fb1e1522982594ef51
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugdynamicfieldcomplus"></a>IDebugDynamicFieldCOMPlus
에 대 한 동적 필드를 나타냅니다는 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugDynamicFieldCOMPlus : IDebugDynamicField  
```  
  
## <a name="methods"></a>메서드  
 메서드 외에도 [IDebugDynamicField](../../../extensibility/debugger/reference/idebugdynamicfield.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetTypeFromPrimitive](../../../extensibility/debugger/reference/idebugdynamicfieldcomplus-gettypefromprimitive.md)|해당 기본 형식이 제공 된 형식을 검색 합니다.|  
|[GetTypeFromTypeDef](../../../extensibility/debugger/reference/idebugdynamicfieldcomplus-gettypefromtypedef.md)|해당 토큰이 지정 된 형식을 검색 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll