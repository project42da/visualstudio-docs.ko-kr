---
title: IDebugFunctionObject2::Evaluate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugFunctionObject2::Evaluate
ms.assetid: bc54c652-904b-4297-a6db-faa329684881
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 58c15872b035660c2e0103a1a9ff69822b250a45
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugfunctionobject2evaluate"></a>IDebugFunctionObject2::Evaluate
함수를 호출 하 고 개체로 결과 값을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Evaluate (  
   IDebugObject** ppParams,  
   DWORD          dwParams,  
   DWORD          dwEvalFlags,  
   DWORD          dwTimeout,  
   IDebugObject** ppResult  
);  
```  
  
```csharp  
int Evaluate (  
   IDebugObject     ppParams,  
   uint             dwParams,  
   uint             dwEvalFlags,  
   uint             dwTimeout,  
   out IDebugObject ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppParams`  
 [in] 배열을 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 입력된 매개 변수를 나타내는 개체입니다. 각 매개이 변수에이 인터페이스에서 만들기 방법 중 하나를 사용 하 여 만들어졌습니다.  
  
 `dwParams`  
 [in] 매개 변수 개수는 `ppParams` 배열입니다.  
  
 `dwEvalFlags`  
 [in] 플래그의 조합 된 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) 계산을 수행할 수는 하는 방법을 지정 하는 열거형입니다.  
  
 `dwTimeout`  
 [in] 이 메서드로부터 반환 하기 전에 대기할 밀리초 단위로 최대 시간을 지정 합니다. 사용 하 여 **무한** 무기한 대기를 나타냅니다.  
  
 `ppResult`  
 [out] 반환 된 **IDebugObject** 함수 개체의 값을 나타내는입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugFunctionObject2](../../../extensibility/debugger/reference/idebugfunctionobject2.md)