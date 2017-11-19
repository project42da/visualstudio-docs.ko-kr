---
title: GETHOSTNAME_TYPE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: GETHOSTNAME_TYPE
helpviewer_keywords: GETHOSTNAME_TYPE enumeration
ms.assetid: 2be92bea-8133-412b-9015-1833baf16e1b
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ba4c0eb77d1eb2a902c9db1288785cf2b6d0ac7a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="gethostnametype"></a>GETHOSTNAME_TYPE
호스트 이름의 형식을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_GETHOSTNAME_TYPE {   
   GHN_FRIENDLY_NAME = 0,  
   GHN_FILE_NAME     = 1  
};  
typedef DWORD GETHOSTNAME_TYPE;  
```  
  
```csharp  
public enum enum_GETHOSTNAME_TYPE {   
   GHN_FRIENDLY_NAME = 0,  
   GHN_FILE_NAME     = 1  
};  
```  
  
## <a name="members"></a>멤버  
 GHN_FRIENDLY_NAME  
 호스트의 이름을 지정합니다.  
  
 GHN_FILE_NAME  
 호스트의 파일 이름을 지정합니다.  
  
## <a name="remarks"></a>설명  
 이러한 값에 대 한 인수로 전달 되는 [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md) 다양 한 형식에 호스트 이름을 검색 하는 메서드입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)