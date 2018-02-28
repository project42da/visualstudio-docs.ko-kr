---
title: BP_PASSCOUNT_STYLE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BP_PASSCOUNT_STYLE
helpviewer_keywords:
- BP_PASSCOUNT_STYLE structure
ms.assetid: 0a647047-e2d5-4724-a0b8-68108425ecad
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e272c92bbcc7364c967fc37c1e57b915e6cb64ab
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="bppasscountstyle"></a>BP_PASSCOUNT_STYLE
발생 하도록 중단점을 발생 시키는 중단점 패스 횟수와 연결 된 조건을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_BP_PASSCOUNT_STYLE {   
   BP_PASSCOUNT_NONE             = 0x0000,  
   BP_PASSCOUNT_EQUAL            = 0x0001,  
   BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,  
   BP_PASSCOUNT_MOD              = 0x0003  
};  
typedef DWORD BP_PASSCOUNT_STYLE;  
```  
  
```csharp  
public enum enum_BP_PASSCOUNT_STYLE {   
   BP_PASSCOUNT_NONE             = 0x0000,  
   BP_PASSCOUNT_EQUAL            = 0x0001,  
   BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,  
   BP_PASSCOUNT_MOD              = 0x0003  
};  
```  
  
## <a name="members"></a>멤버  
 BP_PASSCOUNT_NONE  
 없는 중단점 패스 개수 스타일을 지정 합니다.  
  
 BP_PASSCOUNT_EQUAL  
 같은 중단점 패스 개수 스타일을 설정 합니다. 중단점은 중단점에 적중 횟수 패스 개수 인 경우 발생 합니다.  
  
 BP_PASSCOUNT_EQUAL_OR_GREATER  
 같거나 더 큰를 중단점 패스 개수 스타일을 설정합니다. 중단점은 중단점에 적중 횟수 패스 개수 보다 크거나 같은 경우에 발생 합니다.  
  
 BP_PASSCOUNT_MOD  
 지정 된 모듈로 전달할 수 있습니다. 예를 들어 패스 개수 유형임 `BP_PASSCOUNT_MOD` 패스 개수 값은 4, 적중된 횟수는 4의 배수 때마다 중단점 발생 합니다.  
  
## <a name="remarks"></a>설명  
 에 사용 되는 `stylePassCount` 의 멤버는 [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md) 구조체의 멤버를 차례로 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 및 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)