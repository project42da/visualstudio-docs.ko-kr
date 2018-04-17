---
title: JMC_CODE_SPEC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- JMC_CODE_SPEC
helpviewer_keywords:
- JMC_CODE_SPEC structure
ms.assetid: d89498f1-4234-46d9-b4e2-abbcbca5068a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d3abf59cb55bd64004750be7b24e00e42eb79d9e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="jmccodespec"></a>JMC_CODE_SPEC
이 구조는 모듈에 대 한 JustMyCode 정보를 설정 하는 데 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _JMC_CODE_SPEC {  
   BOOL fIsUserCode;  
   BSTR bstrModuleName;  
} JMC_CODE_SPEC;  
```  
  
```csharp  
public struct JMC_CODE_SPEC {  
   public int    fIsUserCode;  
   public string bstrModuleName;  
};  
```  
  
## <a name="members"></a>멤버  
 fIsUserCode  
 0이 아닌 (`TRUE`) 모듈은 사용자 코드를 고려해 야 하는 경우는 그렇지 않은 경우 0 (`FALSE`) 모듈 외부 코드로 처리 하지 않고는 디버깅 하는 경우.  
  
 bstrModuleName  
 해당 모듈의 이름입니다.  
  
## <a name="remarks"></a>설명  
 이 구조는 이러한 구조를 목록으로 전달 되는 [SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md)