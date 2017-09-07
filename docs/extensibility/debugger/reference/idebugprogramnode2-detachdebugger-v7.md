---
title: IDebugProgramNode2::DetachDebugger_V7 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProgramNode2::DetachDebugger
helpviewer_keywords:
- IDebugProgramNode2::DetachDebugger
- IDebugProgramNode2::DetachDebugger_V7
ms.assetid: d2d4b78e-a2dd-4217-97a6-ab648fd2ee2f
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
ms.openlocfilehash: a281d92d93473dffeb8f488cd802a9cee4a779d7
ms.contentlocale: ko-kr
ms.lasthandoff: 09/06/2017

---
# <a name="idebugprogramnode2detachdebuggerv7"></a>IDebugProgramNode2::DetachDebugger_V7
사용 되지 않습니다. 사용 하지 마십시오.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DetachDebugger_V7 (   
   void   
);  
```  
  
```csharp  
int DetachDebugger_V7 ();  
```  
  
## <a name="return-value"></a>반환 값  
 구현을 항상 반환 `E_NOTIMPL`합니다.  
  
## <a name="remarks"></a>설명  
  
> [!WARNING]
>  일부로 [!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)],이 메서드는 더 이상 사용 하며 항상 반환 `E_NOTIMPL`합니다.  
  
 이 메서드는 디버거 예기치 않게 종료 될 때 호출 됩니다. 이 메서드를 호출할 때는 DE 다시 시작 되는 프로그램에서 분리 된 사용자 인 것 처럼 합니다. 디버그 이벤트를 더 이상 전송 되어야 합니다. 프로그램은 디버거에서의 다른 인스턴스에서 연결 가능한 상태에 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)
