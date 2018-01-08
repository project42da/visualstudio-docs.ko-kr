---
title: IEnumDebugPrograms2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugPrograms2
helpviewer_keywords: IEnumDebugPrograms2
ms.assetid: 7fbb8fb7-db64-4546-a364-dc668430c8af
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: b52c4f28f1f027648674f2be561fc11d7117b6f4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugprograms2"></a>IEnumDebugPrograms2
이 인터페이스는 현재 디버그 세션에서 실행 중인 프로그램을 열거 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IEnumDebugPrograms2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 (DE)는 DE로 디버깅 중인 프로그램의 목록을 제공 하기 위해이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 Visual Studio 호출 [EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md) 이 인터페이스를 가져올 수 있습니다. [EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md) Visual Studio에서 사용 되지 않습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IEnumDebugPrograms2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugprograms2-next.md)|열거 순서에서 프로그램의 지정된 된 수를 검색 합니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugprograms2-skip.md)|열거 순서에서 프로그램의 지정 된 수를 건너뜁니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugprograms2-reset.md)|열거형 시퀀스 시작 부분으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugprograms2-clone.md)|현재 열거자와 동일한 열거 상태가 포함 하는 열거자를 만듭니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugprograms2-getcount.md)|열거자의 프로그램의 수를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 Visual Studio에서는이 인터페이스를 사용합니다.  
  
-   채우기의 **모듈** 창 (호출 하 여 [EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md) 호출한 다음 [EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md) 각 프로그램에 대해).  
  
-   채우기의 **프로세스에 연결** 목록 (호출 하 여 `IDebugProcess2::EnumPrograms` 호출한 다음 [QueryInterface](/cpp/atl/queryinterface) 각 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 는 가져오는인터페이스를[IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md) 인터페이스).  
  
-   프로세스에서 각 프로그램을 디버깅할 수 DEs 목록을 생성 (사용 하 여 [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogram2-getengineinfo.md)).  
  
-   각 프로그램에 편집 하며 계속 (ENC) 업데이트 적용 (IDebugProcess2::EnumPrograms 호출 하 여 다음 호출 [GetENCUpdate](../../../extensibility/debugger/reference/idebugprogram2-getencupdate.md)).  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md)   
 [EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md)