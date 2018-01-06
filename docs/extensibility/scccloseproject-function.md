---
title: "SccCloseProject 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccCloseProject
helpviewer_keywords: SccCloseProject function
ms.assetid: 259c2069-d349-4814-810f-1c3151b7fb84
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 70b0e693f4223c9fe004170a0ed1b4b70c6de442
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="scccloseproject-function"></a>SccCloseProject 함수
이 함수는 특정 세션의 끝을 표시 하는 프로젝트를 닫습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccCloseProject (  
   LPVOID pvContext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pvContext  
 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|프로젝트를 닫았습니다.|  
|SCC_E_PROJNOTOPEN|없는 프로젝트가 현재 열려 있습니다.|  
|SCC_E_NOTAUTHORIZED|사용자가이 작업을 수행할 수 없습니다.|  
|SCC_E_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다.|  
  
## <a name="remarks"></a>설명  
 [SccOpenProject](../extensibility/sccopenproject-function.md) 은 항상이 함수 앞에 호출 됩니다. 이 함수에 대 한 호출을 수행한에 대 한 호출에서 `SccOpenProject` 함수 또는 [SccUninitialize](../extensibility/sccuninitialize-function.md), 소스 제어 시스템에 대 한 연결을 완전히 종료입니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)