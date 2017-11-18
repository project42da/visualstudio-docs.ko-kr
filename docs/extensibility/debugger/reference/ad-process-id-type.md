---
title: AD_PROCESS_ID_TYPE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AD_PROCESS_ID_TYPE
helpviewer_keywords: AD_PROCESS_ID_TYPE enumeration
ms.assetid: 0aab80e9-285a-4697-94ac-c864d42a6aaa
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 75904ef6e06ef7ccd6d126091f8ec0fbe523ac9a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="adprocessidtype"></a>AD_PROCESS_ID_TYPE
프로세스 ID를 해석 하는 방법을 지정 하는 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_AD_PROCESS_ID {  
   AD_PROCESS_ID_SYSTEM = 0,  
   AD_PROCESS_ID_GUID   = 1  
};  
typedef DWORD AD_PROCESS_ID_TYPE;  
```  
  
```csharp  
public enum enum_AD_PROCESS_ID {  
   AD_PROCESS_ID_SYSTEM = 0,  
   AD_PROCESS_ID_GUID   = 1  
};  
```  
  
## <a name="members"></a>멤버  
 AD_PROCESS_ID_SYSTEM  
 프로세스 ID는 시스템 식별자입니다. 사용 하 여는 `ProcessId.dwProcessId` 필드는 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) 구조입니다.  
  
 AD_PROCESS_ID_GUID  
 프로세스 ID는 GUID입니다. 사용 하 여는 `ProcessId.guidProcessId` 필드는 `AD_PROCESS_ID` 구조입니다.  
  
## <a name="remarks"></a>설명  
 에 사용 되는 `ProcessIdType` 의 멤버는 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) 구조에 포함 된 연결 ID의 유형을 식별 하는 구조입니다. 해석 하는 방법을 결정는 `ProcessId` 구조에 결합 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)