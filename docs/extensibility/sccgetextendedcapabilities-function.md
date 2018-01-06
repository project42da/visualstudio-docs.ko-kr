---
title: "SccGetExtendedCapabilities 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccGetExtendedCapabilities
helpviewer_keywords: SccGetExtendedCapabilities function
ms.assetid: 588c6a92-2147-4d8b-a357-96ca7da0a092
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 870d793a11cccdaae9657deabb0e3b08c4d8c6f5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="sccgetextendedcapabilities-function"></a>SccGetExtendedCapabilities 함수
이 함수는 소스 제어 플러그 인에서 지 원하는 추가 기능을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccGetExtendedCapabilities(  
   LPVOID pContext,  
   LONG lSccExCaps,  
   LPBOOL pbSupported  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pContext  
 [in] 소스 제어 플러그 인 컨텍스트 포인터입니다.  
  
 lSccExCaps  
 [in] 확장 된 기능 테스트를 지정 하는 플래그 (확장 된 기능 코드 표를 참조 [기능 플래그](../extensibility/capability-flags.md) 가능한 플래그에 대 한).  
  
 pbSupported  
 [out] 0이 아닌 반환 (`TRUE`) 지정 된 기능이 지원 되 면 그렇지 않으면 0을 반환 합니다 (`FALSE`).  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|Get 기능 작업이 완료 되었습니다.|  
|SCC_E_UNKNOWNERROR<br /><br /> SCC_E_NONSPECIFICERROR|알 수 없거나 지정 되지 않은 오류가 발생 했습니다.|  
  
## <a name="remarks"></a>설명  
 주문형;에이 메서드는 즉, 하는 기능을 테스트 해야 하는 경우이 메서드는 여부를 확인 하려면 기능이 지원 됩니다. 한 번에 하나만 플래그를 지정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [오류 코드](../extensibility/error-codes.md)   
 [기능 플래그](../extensibility/capability-flags.md)