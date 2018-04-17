---
title: IDebugProcess3::DisableENC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProcess3::DisableENC
helpviewer_keywords:
- IDebugProcess3::DisableENC
ms.assetid: cffdbdac-4d76-4aeb-aa55-5d0410db99f1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2da464c82332f6fc4f9bcd57ee8197e111e9fa0a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprocess3disableenc"></a>IDebugProcess3::DisableENC
이 메서드가 명시적으로 편집 하며 계속 하기가 비활성화가이 프로세스에 (및 모든 프로그램 포함). 사용자 지정 포트 공급자는 항상 반환 `E_NOTIMPL`합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DisableENC(  
   EncUnavailableReason reason  
);  
```  
  
```csharp  
   EncUnavailableReason reason  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `reason`  
 [in] 값은 [EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md) 열거 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드를 반환 합니다.  
  
> [!NOTE]
>  사용자 지정 포트 공급자는 항상 반환 `E_NOTIMPL`합니다.  
  
## <a name="remarks"></a>설명  
 한 번 편집 하 고 프로세스를 계속 하기를 사용할 수 없게 됩니다, 그리고 프로세스를 다시 시작 해야만 다시 활성화할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md)