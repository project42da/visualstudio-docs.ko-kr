---
title: SccQueryInfo 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccQueryInfo
helpviewer_keywords:
- SccQueryInfo function
ms.assetid: 3973d336-a9b7-41a2-a4e6-bb8184a96aaf
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5e2838709d7c2c2ad6e6b1eeef36c2cc0018a1a1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="sccqueryinfo-function"></a>SccQueryInfo 함수
이 함수는 소스 제어에서 선택한 파일의 집합에 대 한 상태 정보를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccQueryInfo(  
   LPVOID  pvContext,  
   LONG    nFiles,  
   LPCSTR* lpFileNames,  
   LPLONG  lpStatus  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pvContext  
 [in] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 nFiles  
 [in] 파일에 지정 된 수의 `lpFileNames` 배열과의 길이 `lpStatus` 배열입니다.  
  
 lpFileNames  
 [in] 배열을 쿼리할 수 파일의 이름입니다.  
  
 lpStatus  
 [out에서] 소스 제어 플러그 인에서 각 파일에 대 한 상태 플래그를 반환 하는 배열입니다. 자세한 내용은 참조 [파일 상태 코드](../extensibility/file-status-code-enumerator.md)합니다.  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|쿼리가 성공 했습니다.|  
|SCC_E_ACCESSFAILURE|네트워크 또는 경합 문제 때문일 소스 제어 시스템에 액세스 하는 문제가 발생 했습니다. 다시 시도 하 여 것이 좋습니다.|  
|SCC_E_PROJNOTOPEN|프로젝트 소스 제어에서 열려 있지 않습니다.|  
|SCC_E_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다.|  
  
## <a name="remarks"></a>설명  
 경우 `lpFileName` 빈 문자열인는 현재 업데이트 상태 정보가 없습니다. 그렇지 않으면 변경 상태 정보를 파일의 전체 경로 이름입니다.  
  
 반환 배열의 비트 마스크 될 수 있습니다 `SCC_STATUS_xxxx` 비트입니다. 자세한 내용은 참조 [파일 상태 코드](../extensibility/file-status-code-enumerator.md)합니다. 소스 제어 시스템에는 모든 비트 형식을 지원 하지 않습니다. 예를 들어 경우 `SCC_STATUS_OUTOFDATE` 프린터가 없습니다, 비트가 하지 않을 합니다.  
  
 이 함수를 사용 하 여 파일을 체크 아웃, 다음을 유의 하십시오. `MSSCCI` 상태 요구 사항:  
  
-   `SCC_STATUS_OUTBYUSER` 현재 사용자가 파일을 체크 아웃 하는 경우 설정 됩니다.  
  
-   `SCC_STATUS_CHECKEDOUT` 설정할 수 없습니다 `SCC_STATUS_OUTBYUSER` 설정 됩니다.  
  
-   `SCC_STATUS_CHECKEDOUT` 파일은 체크 아웃할 때 지정 된 작업 디렉터리에만 설정 됩니다.  
  
-   하는 경우 파일은 체크 아웃 된 현재 사용자가 작업 디렉터리가 아닌 다른 디렉터리에 `SCC_STATUS_OUTBYUSER` 설정 되어 있지만 `SCC_STATUS_CHECKEDOUT` 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [파일 상태 코드](../extensibility/file-status-code-enumerator.md)