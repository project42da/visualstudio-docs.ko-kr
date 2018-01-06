---
title: IDebugPortRequest2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPortRequest2
helpviewer_keywords: IDebugPortRequest2 interface
ms.assetid: 556e610d-7c4b-44a8-965a-76a9d02b601a
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5b47a9bde47049c957af9f60e1d09d03b55c2359
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportrequest2"></a>IDebugPortRequest2
이 인터페이스는 포트에 설명 합니다. 이 설명은 포트를 추가할 포트 공급 업체에 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugPortRequest2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 Visual Studio는 일반적으로 포트 공급자에서 디버그 포트를 가져오는 과정에서이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 인터페이스에 전달 되 [포트 추가](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) 디버그 포트를 만듭니다. 에 대 한 호출 [GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md) 나타내는 요청 포트를 처음부터 만드는 데이 인터페이스를 반환 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugPortRequest2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetPortName](../../../extensibility/debugger/reference/idebugportrequest2-getportname.md)|만들려는 포트의 이름을 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 디버그 엔진 일반적으로 포트 공급자 상호 작용 하지 않습니다 있으며,이 인터페이스에 대 한가 사용 되지 않지만 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [포트 추가](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)   
 [GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)