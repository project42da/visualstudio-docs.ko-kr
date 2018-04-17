---
title: GetValidCompatibleFramework 함수 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b28587b44dd98630538bc8d6d04c5bc6049e3ca9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="getvalidcompatibleframework-function"></a>GetValidCompatibleFramework 함수
  이 API는 Office 인프라를 지원 하며 사용자 코드에서 직접 사용할 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT WINAPI GetValidCompatibleFramework(  
    LPCWSTR lpwszCompatibleFrameworksXML,  
    BSTR* pbstrValidFrameworkTag  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|*lpwszCompatibleFrameworksXML*|사용 하지 마십시오.|  
|*pbstrValidFrameworkTag*|사용 하지 마십시오.|  
  
## <a name="return-value"></a>반환 값  
 함수가 성공 하면 반환 **S_OK**합니다. 함수가 실패 하면 오류 코드가 반환 됩니다.  
  
  