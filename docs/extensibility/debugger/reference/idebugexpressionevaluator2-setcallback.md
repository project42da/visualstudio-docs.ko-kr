---
title: IDebugExpressionEvaluator2::SetCallback | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugExpressionEvaluator2::SetCallback
- SetCallback
ms.assetid: 31e3a99e-e784-44a3-8b19-cc5ef31ed546
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a4860418edf2c0dcd4e9d0f6c98ea44db425034e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugexpressionevaluator2setcallback"></a>IDebugExpressionEvaluator2::SetCallback
식 계산기를 (EE) 디버거 엔진 (DE) 메트릭 설정 읽기를 사용 하 여 콜백 인터페이스를 지정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetCallback (  
   IDebugSettingsCallback2* pCallback  
);  
```  
  
```csharp  
int SetCallback (  
   IDebugSettingsCallback2 pCallback  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pCallback`  
 [in] 설정 콜백에 대 한 사용 하는 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 식 계산기 메트릭 설정은 읽는 데 사용할 수 있는 세션 디버그 관리자에 인터페이스를 제공 합니다. 메트릭을 읽을 원격 디버깅에 도움이 될 수는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 컴퓨터입니다.  
  
## <a name="example"></a>예  
 다음 예에서는이 메서드를 구현 하는 방법을 보여 줍니다는 **CEE** 공개 하는 개체는 [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md) 인터페이스입니다.  
  
```cpp  
HRESULT CEE::SetCallback(IDebugSettingsCallback2* in_pCallback)  
{  
    // precondition  
    INVARIANT( this );  
  
    // function body  
    if (NULL != this->m_LanguageSpecificUseCases.pfSetCallback)  
    {  
        EEDomain::fSetCallback DomainVal =  
        {  
            in_pCallback  
        };  
  
        BOOL bSuccess = (*this->m_LanguageSpecificUseCases.pfSetCallback)(DomainVal);  
        ENSURE( bSuccess );  
    }  
  
    // postcondition  
    INVARIANT( this );  
  
    return S_OK;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md)