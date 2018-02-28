---
title: THREADPROPERTY_FIELDS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- THREADPROPERTY_FIELDS
helpviewer_keywords:
- THREADPROPERTY_FIELDS enumeration
ms.assetid: 5b88acb9-03ea-4c29-a788-f0087dccbe23
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 9ff443fc655c18600ff90536d6e7ee5b8aa1ab7f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="threadpropertyfields"></a>THREADPROPERTY_FIELDS
검색 된 스레드에 대 한 정보를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_THREADPROPERTY_FIELDS {   
   TPF_ID           = 0x0001,  
   TPF_SUSPENDCOUNT = 0x0002,  
   TPF_STATE        = 0x0004,  
   TPF_PRIORITY     = 0x0008,  
   TPF_NAME         = 0x0010,  
   TPF_LOCATION     = 0x0020,  
   TPF_ALLFIELDS    = 0xffffffff  
};  
typedef DWORD THREADPROPERTY_FIELDS;  
```  
  
```csharp  
public enum enum_THREADPROPERTY_FIELDS {   
   TPF_ID           = 0x0001,  
   TPF_SUSPENDCOUNT = 0x0002,  
   TPF_STATE        = 0x0004,  
   TPF_PRIORITY     = 0x0008,  
   TPF_NAME         = 0x0010,  
   TPF_LOCATION     = 0x0020,  
   TPF_ALLFIELDS    = 0xffffffff  
};  
```  
  
## <a name="members"></a>멤버  
 TPF_ID  
 초기화/사용 된 `dwThreadId` 필드는 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) 구조입니다.  
  
 TPF_SUSPENDCOUNT  
 초기화/사용 된 `dwSuspendCount` 필드는 `THREADPROPERTIE`S 구조입니다.  
  
 TPF_STATE  
 초기화/사용 된 `dwThreadState` 필드는 `THREADPROPERTIE`S 구조입니다.  
  
 TPF_PRIORITY  
 초기화/사용 된 `bstrPriority` 필드는 `THREADPROPERTIE`S 구조입니다.  
  
 TPF_NAME  
 초기화/사용 된 `bstrName` 필드는 `THREADPROPERTIE`S 구조입니다.  
  
 TPF_LOCATION  
 초기화/사용 된 `bstrLocation` 필드는 `THREADPROPERTIE`S 구조입니다.  
  
 TPF_ALLFIELDS  
 모든 필드를 지정합니다.  
  
## <a name="remarks"></a>설명  
 이러한 값에 대 한 인수로 전달 되는 [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md) 의 필드를 나타내도록 메서드를는 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) 구조를 초기화할 수는 있습니다.  
  
 이러한 값에도 사용 됩니다 `dwFields` 의 멤버는 `THREADPROPERTIES` 구조에는 필드는 사용 되지 않으며 유효한 합니다.  
  
 이러한 플래그 비트와 함께 `OR`합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)   
 [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)