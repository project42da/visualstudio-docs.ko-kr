---
title: IEEVisualizerService::GetPropertyProxy | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEEVisualizerService::GetPropertyProxy
helpviewer_keywords: IEEVisualizerService::GetPropertyProxy method
ms.assetid: 748750f4-76e7-4580-9da2-afba07681b37
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3abde10e53e35b2ad9bc3c95d8b7491292ef8014
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ieevisualizerservicegetpropertyproxy"></a>IEEVisualizerService::GetPropertyProxy
이 메서드는 속성 개체에 대 한 프록시를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetPropertyProxy(  
   DWORD                  dwID,  
   IPropertyProxyEESide** proxy  
);  
```  
  
```csharp  
int GetPropertyProxy(  
   uint                     dwID,  
   out IPropertyProxyEESide proxy  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwID`  
 [in] 검색할 속성 프록시의 ID입니다.  
  
 `proxy`  
 [out] 필요한 프록시에서 구현 되는 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) 형식 시각화 도우미에 대 한이 메서드를 한 지원의 일환으로 요청을 전달 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md)