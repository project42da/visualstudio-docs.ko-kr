---
title: CANSTOP_REASON | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CANSTOP_REASON
helpviewer_keywords: CANSTOP_REASON enumeration
ms.assetid: 6da944eb-36cd-4a8c-8d71-544c775cfcc1
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 98b1e4a9db18490079dd443cb296481aed64376a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="canstopreason"></a>CANSTOP_REASON
프로그램 실행의 특정 지점에 도달한 후 실행을 중지할 수는 경우를 결정 하는 데 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_CANSTOP_REASON {   
   CANSTOP_ENTRYPOINT = 0x0000,  
   CANSTOP_STEPIN     = 0x0001  
};  
typedef DWORD CANSTOP_REASON;  
```  
  
```csharp  
public enum enum_CANSTOP_REASON {   
   CANSTOP_ENTRYPOINT = 0x0000,  
   CANSTOP_STEPIN     = 0x0001  
};  
```  
  
## <a name="members"></a>멤버  
 CANSTOP_ENTRYPOINT  
 지정된 된 프로그램의 진입점을 지정합니다.  
  
 CANSTOP_STEPIN  
 함수를 한 단계씩 실행을 지정 합니다.  
  
## <a name="remarks"></a>설명  
 에 대 한 인수로 전달 되는 [GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md) 함수 또는 메서드를 한 단계씩 실행 후 또는 프로그램의 진입점에 도달한 후 중지를 하는 경우 세션 디버그 관리자 SDM (과)를 확인 하는 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)