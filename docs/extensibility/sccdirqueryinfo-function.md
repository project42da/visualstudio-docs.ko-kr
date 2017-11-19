---
title: "SccDirQueryInfo 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccDirQueryInfo
helpviewer_keywords: SccDirQueryInfo function
ms.assetid: 459e2d99-573d-47c4-b834-6d82c5e14162
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aa1bc3624c8d03cfc484aaace906c2660c3a790e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="sccdirqueryinfo-function"></a>SccDirQueryInfo 함수
이 함수는 현재 상태에 대 한 정규화 된 디렉터리 목록이 있는지 검사합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccDirQueryInfo(  
LPVOID  pContext,  
LONG    nDirs,  
LPCSTR* lpDirNames,  
LPLONG  lpStatus  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pContext  
 [in] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 nDirs  
 [in] 쿼리할 수 선택 디렉터리의 수입니다.  
  
 lpDirNames  
 [in] 배열 쿼리할 디렉터리의 정규화 된 경로입니다.  
  
 lpStatus  
 [out에서] 상태 플래그를 반환 하는 플러그 인 소스 제어에 대 한 배열 구조 (참조 [디렉터리 상태 코드](../extensibility/directory-status-code-enumerator.md) 세부 정보에 대 한).  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|쿼리가 성공 했습니다.|  
|SCC_E_OPNOTSUPPORTED|소스 코드 제어 시스템에서이 작업을 지원 하지 않습니다.|  
|SCC_E_ACCESSFAILURE|소스 제어 시스템에 네트워크 또는 경합 문제 때문에 액세스 하는 문제가 발생 했습니다. 다시 시도 하 여 것이 좋습니다.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|알 수 없는 오류가 발생 했습니다.|  
  
## <a name="remarks"></a>설명  
 함수는 비트 마스크의 비트를 사용 하 여 반환 배열을 채웁니다는 `SCC_DIRSTATUS` 제품군 (참조 [디렉터리 상태 코드](../extensibility/directory-status-code-enumerator.md)), 지정 된 각 디렉터리에 대 한 항목입니다. 에서는 상태 배열은 호출자가 할당 됩니다.  
  
 IDE는이 함수를 사용 하 여 해당 프로젝트를에 있는지 여부를 쿼리하여 소스 제어에서 디렉터리 인지 여부를 확인 한 디렉터리의 이름을 바꿀 전에 합니다. 소스 제어의 디렉터리가 아닌 경우 IDE는 사용자에 게 적절 한 경고를 제공할 수 있습니다.  
  
> [!NOTE]
>  소스 제어 플러그 인을 하는 상태 값 중 하나 이상을 구현 하지 하기로 구현 되지 않은 비트는 0으로 설정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [디렉터리 상태 코드](../extensibility/directory-status-code-enumerator.md)