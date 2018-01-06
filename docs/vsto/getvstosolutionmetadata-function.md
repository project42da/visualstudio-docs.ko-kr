---
title: "GetVstoSolutionMetadata 함수 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
ms.assetid: e8195838-fb9f-42b2-bb76-7ae3753f7751
caps.latest.revision: "6"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 5caba6e6b42eefccfc9dc520758c7dfbc7346844
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getvstosolutionmetadata-function"></a>GetVstoSolutionMetadata 함수
  이 API는 Office 인프라를 지원 하며 사용자 코드에서 직접 사용할 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT WINAPI GetVstoSolutionMetadata(  
    LPCWSTR lpwszSolutionMetadataKey,  
    ISolutionMetadata** ppSolutionInfo  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|*lpwszSolutionMetadataKey*|사용 하지 마십시오.|  
|*ppSolutionInfo*|사용 하지 마십시오.|  
  
## <a name="return-value"></a>반환 값  
 함수가 성공 하면 반환 **S_OK**합니다. 함수가 실패 하면 오류 코드가 반환 됩니다.  
  
  