---
title: BP_FLAGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BP_FLAGS
helpviewer_keywords: BP_FLAGS enumeration
ms.assetid: c45dfc74-5e7f-4f1e-a147-ab2a55dccbd0
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3c4818cca16ffb23429006267829b076d52069c0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="bpflags"></a>BP_FLAGS
중단점을 설정할 때 추가 정보를 지정 하는 데 사용할 수 있는 선택적 플래그를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_BP_FLAGS {   
   BP_FLAG_NONE            = 0x0000,  
   BP_FLAG_MAP_DOCPOSITION = 0x0001,  
   BP_FLAG_DONT_STOP       = 0x0002  
};  
typedef DWORD BP_FLAGS;  
```  
  
```csharp  
public enum enum_BP_FLAGS {   
   BP_FLAG_NONE            = 0x0000,  
   BP_FLAG_MAP_DOCPOSITION = 0x0001,  
   BP_FLAG_DONT_STOP       = 0x0002  
};  
```  
  
## <a name="members"></a>멤버  
 BP_FLAG_NONE  
 중단점 플래그가 지정합니다.  
  
 BP_FLAG_MAP_DOCPOSITION  
 문서 위치를 사용 하 여 중단점을 디버그 엔진 (DE)에 매핑되어야 있는지를 지정 합니다. 스크립트 지향 소스 파일 등 ASP Active Server Pages ()에서 설정 된 중단점에만 적용 됩니다.  
  
 BP_FLAG_DONT_STOP  
 지정 중단점 디버그 엔진에서 처리 되어야 한다는 하지만 디버그 엔진 궁극적으로 중지 해야 함을 하지 있습니다 (즉, 한 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md) 이벤트 개체를 보내지 않아야). 이 플래그는 추적점에서 주로 사용 되는 설계 되었습니다.  
  
## <a name="remarks"></a>설명  
 에 사용 되는 `dwFlags` 의 멤버는 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 및 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) 구조입니다.  
  
 이러한 값에 비트와 함께 사용할 수 있습니다 `OR`합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)   
 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)