---
title: "SccGetUserOption 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccGetUserOption
helpviewer_keywords: SccGetUserOption function
ms.assetid: 17863747-1901-4c53-a2b3-ed996085e120
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ebd59cfada6064d40fe48df3cba4eaac3c3293b5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="sccgetuseroption-function"></a>SccGetUserOption 함수
이 함수는 다양 한 사용자 고유의 옵션을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccGetUserOption(  
   LPVOID pContext,  
   LONG nOption,  
   LPLONG lpVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pContext  
 [in] 소스 제어 플러그 인 컨텍스트 포인터입니다.  
  
 nOption  
 [in] (가능한 옵션에 대 한 설명 참조)를 검색 하는 옵션입니다.  
  
 lpVal  
 [out] 옵션과 관련 된 값입니다.  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|옵션 검색 되었습니다.|  
|SCC_E_OPNOTSUPPORTED|옵션은 지원 되지 않습니다.|  
|SCC_E_NONSPECIFICERROR|지정되지 않은 오류가 발생했습니다.|  
  
## <a name="remarks"></a>설명  
 다음 옵션은이 명령으로 지원 됩니다.  
  
|사용자 옵션|설명|  
|-----------------|-----------------|  
|`SCC_USEROPT_CHECKOUT_LOCALVER`|사용자가 파일의 로컬 버전 체크 아웃을 여부를 결정 합니다. `lpVal`할당 된 `SCC_USEROPT_COLV_YES` (사용자가 로컬 파일을 체크 아웃) 또는 `SCC_USEROPT_COLV_NO`합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [오류 코드](../extensibility/error-codes.md)