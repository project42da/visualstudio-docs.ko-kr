---
title: BP_FLAGS90 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BP_FLAGS90 enumeration
ms.assetid: 3e5a06c5-fb30-4b8a-b2d5-4a0570fc80bd
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 5e958be77ca266af30556fa8c03c580eea94b903
ms.contentlocale: ko-kr
ms.lasthandoff: 09/06/2017

---
# <a name="bpflags90"></a>BP_FLAGS90
선택적 플래그에 대 한 유효한 값을 열거합니다. 중단점을 설정할 때 추가 정보를 지정 하는 선택적 플래그를 사용할 수 있습니다. 이 열거형 확장는 [BP_FLAGS](../../../extensibility/debugger/reference/bp-flags.md) 열거 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_BP_FLAGS90  
{  
   // VS 8.0 values  
   BP90_FLAG_NONE               = 0x0000,  
   BP90_FLAG_MAP_DOCPOSITION    = 0x0001,  
   BP90_FLAG_DONT_STOP          = 0x0002,  
  
   // Values added in VS 9.0  
   BP90_FLAG_TRACEPOINT_CONTINUE = 0x0004,  
};  
typedef DWORD BP_FLAGS90;  
```  
  
```csharp  
public enum enum_BP_FLAGS90  
{  
   // VS 8.0 values  
   BP90_FLAG_NONE                = 0x0000,  
   BP90_FLAG_MAP_DOCPOSITION     = 0x0001,  
   BP90_FLAG_DONT_STOP           = 0x0002,  
  
   // Values added in VS 9.0  
   BP90_FLAG_TRACEPOINT_CONTINUE = 0x0004,  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 BP90_FLAG_NONE  
 중단점 플래그가 지정합니다.  
  
 BP90_FLAG_MAP_DOCPOSITION  
 디버그 엔진 (DE) 문서 위치를 사용 하 여 중단점을 매핑하는 것을 지정 합니다. 스크립트 지향 소스 파일 등 ASP Active Server Pages ()에서 설정 된 중단점에만 적용 됩니다.  
  
 BP90_FLAG_DONT_STOP  
 지정 중단점 디버그 엔진에서 처리 되어야 한다는 하지만 디버그 엔진 궁극적으로 중지 해야 함이 없습니다. 즉, 한 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md) 이벤트 개체를 보내지 않아야 합니다. 이 플래그는 주로 추적 지점에서 사용 되는 설계 되었습니다.  
  
 BP90_FLAG_TRACEPOINT_CONTINUE  
 네이티브 디버그 엔진에서 단계별 실행 상태를 선택 취소 해야 하는지 여부를 결정 하는 데 사용 합니다. BP90_FLAG_DONT_STOP 추적 지점에 매크로 실행 하는 경우 설정 되어 있지 않으므로 BP90_FLAG_DONT_STOP에서 다릅니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Msdbg90.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
