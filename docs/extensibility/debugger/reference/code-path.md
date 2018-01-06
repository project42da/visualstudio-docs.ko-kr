---
title: CODE_PATH | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CODE_PATH
helpviewer_keywords: CODE_PATH structure
ms.assetid: 2d4b2890-4c9d-47e1-83c0-df9c6436427f
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: dd2cd5de0d415e133beb6b72b63b9d42eb61c947
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="codepath"></a>CODE_PATH
메서드 또는 함수 호출에 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct tagCODE_PATH {   
   BSTR                bstrName;  
   IDebugCodeContext2* pCode;  
} CODE_PATH;  
```  
  
```csharp  
public struct CODE_PATH {  
   public string            bstrName;  
   public IDebugCodeContext pCode;  
}  
```  
  
## <a name="members"></a>멤버  
 bstrName  
 코드 경로의 이름입니다.  
  
 pCode  
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 함수 한 단계씩 코드에서 위치 식별 하는 개체입니다.  
  
## <a name="remarks"></a>설명  
 이 구조는 함수를 한 단계씩 실행을 구현 하는 데 사용 됩니다. [EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md) 디버깅 중인 프로그램의 현재 위치에서 모든 호출을 반환 합니다. 이 구조는 이러한 한 호출을 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md)