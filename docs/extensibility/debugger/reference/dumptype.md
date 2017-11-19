---
title: DUMPTYPE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DUMPTYPE
helpviewer_keywords: DUMPTYPE enumeration
ms.assetid: ea8160db-8732-4056-a1d7-892ef72da71e
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 26e2836215ac5563a6ebaefb9d31d682348c7e89
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="dumptype"></a>DUMPTYPE
마찬가지로 덤프 하려면 프로그램의 상태 (예: 실행 중인 스레드, 스택 프레임 및 현재 명령의 주소)의 크기를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_DUMPTYPE {   
   DUMP_MINIDUMP = 0,  
   DUMP_FULLDUMP = 1  
};  
typedef DWORD DUMPTYPE;  
```  
  
```csharp  
public enum enum_DUMPTYPE {   
   DUMP_MINIDUMP = 0,  
   DUMP_FULLDUMP = 1  
};  
```  
  
## <a name="members"></a>멤버  
 DUMP_MINIDUMP  
 작은 하 고 간단한 덤프를 지정합니다.  
  
 DUMP_FULLDUMP  
 대규모의 전체 덤프를 지정합니다.  
  
## <a name="remarks"></a>설명  
 에 대 한 인수로 전달 되는 [WriteDump](../../../extensibility/debugger/reference/idebugprogram2-writedump.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [WriteDump](../../../extensibility/debugger/reference/idebugprogram2-writedump.md)