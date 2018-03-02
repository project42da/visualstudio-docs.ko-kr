---
title: PROCESS_INFO_FLAGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PROCESS_INFO_FLAGS
helpviewer_keywords:
- PROCESS_INFO_FLAGS enumeration
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 6e95e9f66b804fed102c0d51aa17a1bfe4f51ca5
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2018
---
# <a name="processinfoflags"></a>PROCESS_INFO_FLAGS

또는 설명 하는 프로세스의 속성을 지정 합니다.

## <a name="syntax"></a>구문

```cpp
enum enum_PROCESS_INFO_FLAGS { 
   PIFLAG_SYSTEM_PROCESS    = 0x00000001,
   PIFLAG_DEBUGGER_ATTACHED = 0x00000002,
   PIFLAG_PROCESS_STOPPED   = 0x00000004,
   PIFLAG_PROCESS_RUNNING   = 0x00000008,
};
typedef DWORD PROCESS_INFO_FLAGS;
```

```csharp
enum enum_PROCESS_INFO_FLAGS { 
   PIFLAG_SYSTEM_PROCESS    = 0x00000001,
   PIFLAG_DEBUGGER_ATTACHED = 0x00000002,
   PIFLAG_PROCESS_STOPPED   = 0x00000004,
   PIFLAG_PROCESS_RUNNING   = 0x00000008,
};
```

## <a name="members"></a>멤버

PIFLAG_SYSTEM_PROCESS  
프로세스는 시스템 프로세스 임을 나타냅니다.

PIFLAG_DEBUGGER_ATTACHED  
디버거에 의해 프로세스가 디버깅 되 고 있는지를 나타냅니다. 수도 있습니다는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 디버거, 또는 몇 가지 다른 디버거, 예를 들어 WinDbg를 일 수 있습니다.

PIFLAG_PROCESS_STOPPED  
프로세스 중지 되었음을 나타냅니다. 경우에만 유효한 `PIFLAG_DEBUGGER_ATTACHED` 도 지정 합니다. Visual Studio 2005에서 이상에서 사용할 수 있습니다.

PIFLAG_PROCESS_RUNNING  
프로세스가 실행 되는 것을 나타냅니다. 경우에만 유효한 `PIFLAG_DEBUGGER_ATTACHED` 도 지정 합니다. Visual Studio 2005에서 이상에서 사용할 수 있습니다.

## <a name="remarks"></a>설명

에 사용 되는 `Flags` 의 멤버는 [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) 구조입니다.

이러한 플래그 비트와 함께 `OR`합니다.

## <a name="requirements"></a>요구 사항

헤더: msdbg.h

Namespace: Microsoft.VisualStudio.Debugger.Interop

Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목

[열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)