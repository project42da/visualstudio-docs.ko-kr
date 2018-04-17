---
title: IEnumDebugFrameInfo2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IEnumDebugFrameInfo2
helpviewer_keywords:
- IEnumDebugFrameInfo2
ms.assetid: 994e30ad-435a-4f9e-9272-d96d9e01099c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 858250c3c951880cf905ea6ee150f1ff61008204
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ienumdebugframeinfo2"></a>IEnumDebugFrameInfo2
이 인터페이스를 열거 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```  
IEnumDebugFrameInfo2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 현재 호출 스택을 설명 하는 구조체의 목록을 제공 하기 위해이 인터페이스를 구현 하는 디버그 엔진 (DE).  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 Visual Studio 호출 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) 중단점 될 때마다이 인터페이스를 가져오려면 예외 또는 중단 발생 디버깅 중인 프로그램에 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IEnumDebugFrameInfo2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugframeinfo2-next.md)|지정된 된 수의 검색 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 열거형 시퀀스에는 구조입니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugframeinfo2-skip.md)|지정 된 개수의 건너뜁니다 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 열거형 시퀀스에는 구조입니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugframeinfo2-reset.md)|열거형 시퀀스 시작 부분으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugframeinfo2-clone.md)|현재 열거자와 동일한 열거 상태가 포함 하는 열거자를 만듭니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugframeinfo2-getcount.md)|개수를 가져옵니다 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 구조에는 열거자입니다.|  
  
## <a name="remarks"></a>설명  
 Visual Studio 중단점, 예외 또는 사용자에서 생성 된 일시 중지 디버깅 중인 프로그램에서 처리 하는 첫 번째 단계로이 인터페이스를 가져옵니다. 목록이 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 구조 현재 호출 스택을 나타냅니다, 목록 및 가장 오래 된 기능을 처음부터 현재 함수 호출으로는 목록의 끝에서 호출 합니다. 각 `FRAMEINFO` 식을 계산할 수 및 지역 변수를 살펴 컨텍스트 스택 프레임을 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)   
 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)