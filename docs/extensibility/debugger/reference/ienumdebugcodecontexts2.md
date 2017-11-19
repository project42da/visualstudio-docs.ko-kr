---
title: IEnumDebugCodeContexts2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugCodeContexts2
helpviewer_keywords: IEnumDebugCodeContexts2
ms.assetid: 72915146-215f-4c99-a034-131b2b474e0e
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9d0d54e9a3987ab8b2493d9e999955febd73ac4a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ienumdebugcodecontexts2"></a>IEnumDebugCodeContexts2
이 인터페이스는 디버그 세션 나 연결 된 특정 프로그램이 나 문서 코드 컨텍스트를 열거 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IEnumDebugCodeContexts2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 (DE) 프로그램에서 특정 텍스트 위치에 대 한 컨텍스트를 코드의 목록 또는 특정 문서 컨텍스트에 대 한 코드 컨텍스트의 목록을 나타내는 데이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 호출 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md) 프로그램의 소스 문서에서 특정 텍스트 위치에 대 한 컨텍스트를 코드의 목록을 나타내는이 인터페이스를 가져올 수 있습니다.  
  
 호출 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md) 특정 원본 문서에 있는 모든 코드 컨텍스트에서의 목록을 나타내는이 인터페이스를 가져올 수 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IEnumDebugCodeContexts2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-next.md)|열거형 시퀀스에 있는 코드 컨텍스트에서 지정된 된 수를 검색합니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-skip.md)|열거형 시퀀스에 있는 코드 컨텍스트에서 지정된 된 수를 건너뜁니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-reset.md)|열거형 시퀀스 시작 부분으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-clone.md)|현재 열거자와 동일한 열거 상태가 포함 하는 열거자를 만듭니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-getcount.md)|열거자에서 코드 컨텍스트의 수를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 Visual Studio 호출 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md) 코드 컨텍스트의 목록을 채우는 데 선택할 수 있습니다 때 다음 문을 설정 또는 소스 파일에 대 한 디스어셈블리를 표시 합니다. 예를 들어 c + + 스타일 서식 파일의 여러 인스턴스가 있는 경우 여러 코드 컨텍스트에서 발생할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)   
 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md)