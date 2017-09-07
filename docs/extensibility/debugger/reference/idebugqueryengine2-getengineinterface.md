---
title: IDebugQueryEngine2::GetEngineInterface | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugQueryEngine2::GetEngineInterface
helpviewer_keywords:
- IDebugQueryEngine2::GetEngineInterface
ms.assetid: ed84aa98-7ec7-48f3-97ae-821090bc3664
caps.latest.revision: 9
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
ms.openlocfilehash: 598606c6360993e664eda19e30b1a8b017a59e3a
ms.contentlocale: ko-kr
ms.lasthandoff: 09/06/2017

---
# <a name="idebugqueryengine2getengineinterface"></a>IDebugQueryEngine2::GetEngineInterface
사용자 지정 디버그 엔진 (DE) 인터페이스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetEngineInterface(   
   IUnknown** ppUnk  
);  
```  
  
```csharp  
int GetEngineInterface(   
   out object ppUnk  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppUnk`  
 [out] 반환 된 `IUnknown` 디버그 엔진 (DE)와 DE와 관련 된 다른 모든 유효한 인터페이스에 대 한 쿼리 될 수 있는 개체를 나타냅니다 (예를 들어 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) 또는 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)).  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 결과 인터페이스 호출에서이 메서드 검색 하는 인터페이스를 통해 세션 디버그 관리자의 처리를 우회 하 고 SDM에 잘못 된 상태 또는 디버깅 하는 동안 오류를 생성 될 수 있습니다 주의 하 여 사용 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugQueryEngine2](../../../extensibility/debugger/reference/idebugqueryengine2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)
