---
title: EncUnavailableReason | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- EncUnavailableReason
helpviewer_keywords:
- EncUnavailableReason enumeration
ms.assetid: c10aa4c0-d7e0-4de1-b8ff-7e050985eb12
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4dcf705015925145b790b14a44007fed8d8fad3b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="encunavailablereason"></a>EncUnavailableReason
`This is for internal use only!` 이유를 나타내는 **편집 하며 계속 하기** 를 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum tagEncUnavailableReason {  
   ENCUN_NONE,  
   ENCUN_INTEROP,  
   ENCUN_SQLCLR,  
   ENCUN_MINIDUMP,  
   ENCUN_EMBEDDED,  
   ENCUN_ATTACH,  
   ENCUN_WIN64  
};  
typedef enum tagEncUnavailableReason EncUnavailableReason;  
```  
  
```csharp  
public enum EncUnavailableReason {  
   ENCUN_NONE,  
   ENCUN_INTEROP,  
   ENCUN_SQLCLR,  
   ENCUN_MINIDUMP,  
   ENCUN_EMBEDDED,  
   ENCUN_ATTACH,  
   ENCUN_WIN64  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 ENCUN_NONE  
 편집 하며 계속 하기 사용할 수 없는 특정 이유가 없습니다.  
  
 ENCUN_INTEROP  
 InterOp 호출 하는 동안 편집 하며 계속 하기를 사용할 수 없습니다.  
  
 ENCUN_SQLCLR  
 공용 언어 런타임 (CLR)를 사용 하는 SQL 프로시저 호출 시 편집 하며 계속 하기를 사용할 수 없습니다.  
  
 ENCUN_MINIDUMP  
 미니 덤프를 처리 하는 동안 편집 하며 계속 하기를 사용할 수 없습니다.  
  
 ENCUN_EMBEDDED  
 편집 하며 계속 하기 사용할 수 없는 경우 포함 된 코드를 처리 하는 경우  
  
 ENCUN_ATTACH  
 편집 하며 계속 사용할 수 없는 세션에 연결 된 경우 때문에 시작 되지 않은 디버거에 의해 합니다.  
  
 ENCUN_WIN64  
 64 비트 Windows 코드를 처리 하는 동안 편집 하며 계속 하기를 사용할 수 없습니다.  
  
## <a name="remarks"></a>설명  
 이 열거형은 내부 용도로 여 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]합니다. [GetENCAvailableState](../../../extensibility/debugger/reference/idebugprocess3-getencavailablestate.md) 및 [DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md) 사용자 지정 포트 공급자에 의해 구현 된 메서드는 항상 반환 `E_NOTIMPL`합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.idl  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md)   
 [GetENCAvailableState](../../../extensibility/debugger/reference/idebugprocess3-getencavailablestate.md)