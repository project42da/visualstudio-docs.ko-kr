---
title: IDebugEvent2::GetAttributes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEvent2::GetAttributes
helpviewer_keywords: IDebugEvent2::GetAttributes
ms.assetid: 2ac5b5fb-da17-43f7-811a-313f677e60d7
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ff7b568feb2eddff3d712c494e610fc6b9a6b262
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugevent2getattributes"></a>IDebugEvent2::GetAttributes
이 디버그 이벤트에 대 한 특성을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetAttribute(   
   DWORD* pdwAttrib  
);  
```  
  
```csharp  
int GetAttribute(   
   out uint pdwAttrib  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwAttrib`  
 [out] 플래그의 조합 된 [EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md) 열거 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 인터페이스는 모든 이벤트에 공통적으로 적용 합니다. 이 메서드 이벤트의 형식을 설명합니다 예를 들어 이벤트 동기 또는 비동기 이며는 stopping 이벤트입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md)