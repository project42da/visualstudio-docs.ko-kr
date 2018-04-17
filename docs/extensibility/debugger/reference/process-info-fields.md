---
title: PROCESS_INFO_FIELDS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- PROCESS_INFO_FIELDS
helpviewer_keywords:
- PROCESS_INFO_FIELDS enumeration
ms.assetid: 0d9cc345-3d3a-44d8-ae15-a67acb97a828
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3376db379e4e911bcaa8e865a16c63d1251229f6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="processinfofields"></a>PROCESS_INFO_FIELDS
어떤 종류의 정보를 프로세스에 대 한 검색을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_PROCESS_INFO_FIELDS {   
   PIF_FILE_NAME             = 0x00000001,  
   PIF_BASE_NAME             = 0x00000002,  
   PIF_TITLE                 = 0x00000004,  
   PIF_PROCESS_ID            = 0x00000008,  
   PIF_SESSION_ID            = 0x00000010,  
   PIF_ATTACHED_SESSION_NAME = 0x00000020,  
   PIF_CREATION_TIME         = 0x00000040,  
   PIF_FLAGS                 = 0x00000080,  
   PIF_ALL                   = 0x000000ff  
};  
typedef DWORD PROCESS_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_PROCESS_INFO_FIELDS {   
   PIF_FILE_NAME             = 0x00000001,  
   PIF_BASE_NAME             = 0x00000002,  
   PIF_TITLE                 = 0x00000004,  
   PIF_PROCESS_ID            = 0x00000008,  
   PIF_SESSION_ID            = 0x00000010,  
   PIF_ATTACHED_SESSION_NAME = 0x00000020,  
   PIF_CREATION_TIME         = 0x00000040,  
   PIF_FLAGS                 = 0x00000080,  
   PIF_ALL                   = 0x000000ff  
};  
```  
  
## <a name="members"></a>멤버  
 PIF_FILE_NAME  
 초기화/사용 된 `bstrFileName` 필드는 [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) 구조입니다.  
  
 PIF_BASE_NAME  
 초기화/사용 된 `bstrBaseName` 필드는 `PROCESS_INFO` 구조입니다.  
  
 PIF_TITLE  
 초기화/사용 된 `bstrTitle` 필드는 `PROCESS_INFO` 구조입니다.  
  
 PIF_PROCESS_ID  
 초기화/사용 된 `ProcessId` 필드는 `PROCESS_INFO` 구조입니다.  
  
 PIF_SESSION_ID  
 초기화/사용 된 `dwSessionId` 필드는 `PROCESS_INFO` 구조입니다.  
  
 PIF_ATTACHED_SESSION_NAME  
 초기화/사용 된 `bstrAttachedSessionName` 필드는 `PROCESS_INFO` 구조입니다.  
  
 PIF_CREATION_TIME  
 초기화/사용 된 `CreationTime` 필드는 `PROCESS_INFO` 구조입니다.  
  
 PIF_FLAGS  
 초기화/사용 된 `Flags` 필드는 `PROCESS_INFO` 구조입니다.  
  
 PIF_ALL  
 모든 필드를 채웁니다.  
  
## <a name="remarks"></a>설명  
 에 전달 되는 [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md) 의 필드를 나타내도록 메서드를는 [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) 구조를 초기화할 수는 있습니다.  
  
 에 사용 `Fields` 필드는 `PROCESS_INFO` 구조에는 필드는 사용 되지 않으며 유효한 합니다.  
  
 이러한 플래그 비트와 함께 `OR`합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)