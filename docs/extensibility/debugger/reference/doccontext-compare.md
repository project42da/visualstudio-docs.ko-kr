---
title: DOCCONTEXT_COMPARE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DOCCONTEXT_COMPARE
helpviewer_keywords:
- DOCCONTEXT_COMPARE enumeration
ms.assetid: ed947c34-b07e-4b69-8381-b6e7cb842862
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 77c810bb6e4791fbc0c3cf787f340a8d996ce037
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="doccontextcompare"></a>DOCCONTEXT_COMPARE
두 문서 컨텍스트를 비교 하기 위한 조건을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
typedef DWORD DOCCONTEXT_COMPARE;  
```  
  
```csharp  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
```  
  
## <a name="members"></a>멤버  
 DOCCONTEXT_EQUAL  
 해당 대상 문서 컨텍스트를 사용 하는 목록에서 첫 번째 문서 컨텍스트를 찾습니다.  
  
 DOCCONTEXT_LESS_THAN  
 대상 문서 컨텍스트에서 가져왔습니다 보다 작은 목록에서 첫 번째 문서 컨텍스트를 찾습니다.  
  
 DOCCONTEXT_GREATER_THAN  
 대상 문서 컨텍스트에서 가져왔습니다 보다 큰 목록에서 첫 번째 문서 컨텍스트를 찾습니다.  
  
 DOCCONTEXT_SAME_DOCUMENT  
 대상 문서 컨텍스트에서 가져왔습니다와 동일한 문서에 있는 목록의 첫 번째 문서 컨텍스트를 찾습니다.  
  
## <a name="remarks"></a>설명  
 에 대 한 인수로 전달 되는 [비교](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md) 메서드.  
  
 이러한 값은 목록에서 첫 번째 문서 컨텍스트를 찾는 데 필요한 비교 기준을 지정 하는 데 사용 됩니다. 문서 컨텍스트를 통해 자체 작업에 대해 비교할 문서 컨텍스트의 목록을 제공할는 `IDebugDocumentContext2::Compare` 메서드. 비교 연산자는 목록의 첫 번째 문서 컨텍스트 `true` 반환 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Compare](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)
