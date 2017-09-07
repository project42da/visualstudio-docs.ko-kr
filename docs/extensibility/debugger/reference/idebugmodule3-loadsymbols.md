---
title: IDebugModule3::LoadSymbols | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugModule3::LoadSymbols
helpviewer_keywords:
- IDebugModule3::LoadSymbols
ms.assetid: 7548c8c1-cbc6-48aa-a845-19058d4a85bb
caps.latest.revision: 11
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
ms.openlocfilehash: 00b357a7c122de2788875632b770c4346963d975
ms.contentlocale: ko-kr
ms.lasthandoff: 09/06/2017

---
# <a name="idebugmodule3loadsymbols"></a>IDebugModule3::LoadSymbols
현재 모듈에 대 한 기호를 로드합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT LoadSymbols(  
   void  
);  
```  
  
```csharp  
int LoadSymbols();  
```  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 반환 `S_OK`합니다. 실패 한 경우 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 현재 검색 경로에서 기호를 로드 합니다 (호출 하 여 변경할 수 있습니다는 [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md) 메서드).  
  
 이 메서드는 기본적으로 [ReloadSymbols_Deprecated](../../../extensibility/debugger/reference/idebugmodule2-reloadsymbols-deprecated.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)   
 [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)
