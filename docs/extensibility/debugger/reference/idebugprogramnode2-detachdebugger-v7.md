---
title: IDebugProgramNode2::DetachDebugger_V7 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgramNode2::DetachDebugger
helpviewer_keywords:
- IDebugProgramNode2::DetachDebugger
- IDebugProgramNode2::DetachDebugger_V7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3a79c073048fe30a4abed069487ad09943253475
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprogramnode2detachdebuggerv7"></a>IDebugProgramNode2::DetachDebugger_V7

> [!Note]
> 사용 되지 않습니다. 사용 하지 마십시오.

## <a name="syntax"></a>구문

```cpp
HRESULT DetachDebugger_V7 (
   void 
);
```

```csharp
int DetachDebugger_V7 ();
```

## <a name="return-value"></a>반환 값

구현을 항상 반환 `E_NOTIMPL`합니다.

## <a name="remarks"></a>설명

> [!WARNING]
> Visual Studio 2005를 기준으로이 메서드는 더 이상 사용 하며 항상 반환 `E_NOTIMPL`합니다.

이 메서드는 디버거 예기치 않게 종료 될 때 호출 됩니다. 이 메서드를 호출할 때는 DE 다시 시작 되는 프로그램에서 분리 된 사용자 인 것 처럼 합니다. 디버그 이벤트를 더 이상 전송 되어야 합니다. 프로그램은 디버거에서의 다른 인스턴스에서 연결 가능한 상태에 있어야 합니다.

## <a name="see-also"></a>참고 항목

[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)