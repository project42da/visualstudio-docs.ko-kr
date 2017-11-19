---
title: IDebugProperty3::CreateObjectID | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProperty3::CreateObjectID
helpviewer_keywords: IDebugProperty3::CreateObjectID
ms.assetid: f2fa81e7-822f-456e-8729-a96a18eea771
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 363a43c71a6812ee69e1fda5778eb992579e9c76
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugproperty3createobjectid"></a>IDebugProperty3::CreateObjectID
다른 모든 속성 간에 고유한 지 확인 하려면이 속성에 대 한 고유 ID를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateObjectID(  
   void  
);  
```  
  
```csharp  
int CreateObjectID();  
```  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 디버그 세션 관리자가 다른 모든 속성과 함께이 속성은 고유 하 게 식별 하 고 있는지 확인 하려고 할 때 호출 됩니다. 디버그 엔진 (DE) 대처 속성 이미 고유 하 게 식별 하지 않는 한이 메서드를 지원 합니다. 반환 된 DE이이 메서드를 지원 하지 않는 경우 `E_NOTIMPL`합니다.  
  
 모든 고유 ID를 사용 하 여 만든 `CreateObjectID` 때 소멸 되는 [DestroyObjectID](../../../extensibility/debugger/reference/idebugproperty3-destroyobjectid.md) 메서드는;이 끝났음을 신호로 보냅니다.이 속성을 고유 하 게 식별 하는 데 필요 합니다.  
  
> [!NOTE]
>  메서드가 DE의 고유 id가 무엇이 든 수행할 수 있도록이 고유 ID를 검색할 수 없는 경우는 `CreateObjectID` 메서드를 호출 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [DestroyObjectID](../../../extensibility/debugger/reference/idebugproperty3-destroyobjectid.md)