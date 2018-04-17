---
title: DISASSEMBLY_STREAM_SCOPE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DISASSEMBLY_STREAM_SCOPE
helpviewer_keywords:
- DISASSEMBLY_STREAM_SCOPE enumeration
ms.assetid: 43e2b364-cbbe-4755-a7e6-a03f3054c965
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a0c72d0f14da9840c0a77d5ae88cb0acb5b54cba
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="disassemblystreamscope"></a>DISASSEMBLY_STREAM_SCOPE
디스어셈블리 스트림의 범위를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_DISASSEMBLY_STREAM_SCOPE {   
   DSS_HUGE     = 0x10000000,  
   DSS_FUNCTION = 0x0001,  
   DSS_MODULE   = (DSS_HUGE) | 0x0002,  
   DSS_ALL      = (DSS_HUGE) | 0x0003  
};  
typedef DWORD DISASSEMBLY_STREAM_SCOPE;  
```  
  
```csharp  
public enum enum_DISASSEMBLY_STREAM_SCOPE {   
   DSS_HUGE     = 0x10000000,  
   DSS_FUNCTION = 0x0001,  
   DSS_MODULE   = (DSS_HUGE) | 0x0002,  
   DSS_ALL      = (DSS_HUGE) | 0x0003  
};  
```  
  
## <a name="members"></a>멤버  
 DSS_HUGE  
 코드 컨텍스트를 분해는 클라이언트를 한 번의 호출을 검색 하려면 일반적으로 보다 더 많은 출력을 생성 하도록 지정 합니다.  
  
 DSS_FUNCTION  
 코드 컨텍스트에 포함 된 함수를 디스어셈블할 수를 지정 합니다. 디스어셈블리 스트림을 나타냄을 지정는 함수에서 반환 하는 경우는 [GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md) 메서드.  
  
 DSS_MODULE  
 반환 하는 경우는 `IDebugDisassemblyStream2::GetScope` 메서드를 디스어셈블리 스트림 모듈을 나타냄을 지정 합니다.  
  
 DSS_ALL  
 전체 주소 공간에 대 한 디스어셈블리를 지정합니다.  
  
## <a name="remarks"></a>설명  
 에 대 한 인수로 전달 되는 [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md) 메서드 반환한는 [GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md) 메서드.  
  
 이러한 값에 비트와 함께 사용할 수 있습니다 `OR`합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)   
 [GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md)