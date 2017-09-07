---
title: IDebugReference2::GetDerivedMostReference | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugReference2::GetDerivedMostReference
helpviewer_keywords:
- IDebugReference2::GetDerivedMostReference
ms.assetid: 07253b74-7d39-48e0-8e85-ac8dfd919f6e
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
ms.openlocfilehash: 9c52e0deb9303790a10091bf645646546aef546d
ms.contentlocale: ko-kr
ms.lasthandoff: 09/06/2017

---
# <a name="idebugreference2getderivedmostreference"></a>IDebugReference2::GetDerivedMostReference
참조의 가장 많이 파생 참조를 가져옵니다. 나중에 사용하기 위해 예약되어 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetDerivedMostReference(   
   IDebugReference2** ppDerivedMost  
);  
```  
  
```csharp  
int GetDerivedMostReference(   
   out IDebugReference2 ppDerivedMost  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppDerivedMost`  
 [out] 반환 된 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 가장 많이 파생 속성을 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 항상 `E_NOTIMPL`를 반환합니다.  
  
## <a name="remarks"></a>설명  
 예를 들어,이 속성을 구현 하는 개체를 설명 하는 경우 `ClassRoot` 의 인스턴스인 실제로 하지만 `ClassDerived` 에서 파생 된 `ClassRoot`,이 메서드는 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 개체 에 대 한 참조를 나타내는 `ClassDerived` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)
