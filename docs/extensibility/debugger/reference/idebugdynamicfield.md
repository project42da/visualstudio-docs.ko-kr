---
title: IDebugDynamicField | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDynamicField
helpviewer_keywords: IDebugDynamicField interface
ms.assetid: caffbd95-7596-4714-84b1-b964e89a78bb
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d1fdd5e0eeb7aeb88b999e72dac875a41c0e0b03
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdynamicfield"></a>IDebugDynamicField
이 인터페이스에는 변수의 형식을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugDynamicField : IDebugField  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 이 인터페이스는 런타임 시 확인할 수 있는 모든 형식에 대 한 기본 클래스로 기호 공급자에 의해 구현 됩니다. 이 관리 되는 코드의 경우에 해당 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 인터페이스는 더욱 특수화 된 인터페이스 파생 하는 데 사용 될 수 있는 기본 클래스를 나타냅니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 이 인터페이스에서 상속 된 것과 다른 모든 메서드를 제공 하지 않는 `IDebugField`합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)