---
title: "SccUncheckout 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccUncheckout
helpviewer_keywords: SccUncheckout function
ms.assetid: 6d498b70-29c7-44b7-ae1c-7e99e488bb09
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f9b4b2f06b8ee020ca07e780836ec2abbbc96e82
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="sccuncheckout-function"></a>SccUncheckout 함수
이 함수에는 선택한 파일 또는 파일의 내용을 체크 아웃 이전 상태로 복원 하는 이전 체크 아웃 작업을 실행 취소 합니다. 파일 체크 아웃 이후에 발생 한 모든 변경 내용이 손실 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccUncheckout (  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pvContext  
 [in] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 hWnd  
 [in] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에를 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 nFiles  
 [in] 에 지정 된 파일의 수는 `lpFileNames` 배열입니다.  
  
 lpFileNames  
 [in] 체크 아웃을 취소 하려는 파일의 정규화 된 로컬 경로 이름 배열입니다.  
  
 fOptions  
 [in] 명령 플래그 (사용 되지 않음)입니다.  
  
 pvOptions  
 [in] 소스 제어 플러그 인에 대 한 옵션입니다.  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|체크 아웃을 취소 했습니다.|  
|SCC_E_FILENOTCONTROLLED|선택한 파일은 소스 코드 제어 하지 않습니다.|  
|SCC_E_ACCESSFAILURE|소스 제어 시스템에 네트워크 또는 경합 문제 때문에 액세스 하는 문제가 발생 했습니다. 다시 시도 하 여 것이 좋습니다.|  
|SCC_E_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다. 실행 취소 체크 아웃 하지 못했습니다.|  
|SCC_E_NOTCHECKEDOUT|사용자는 파일을 체크 아웃가 없습니다.|  
|SCC_E_NOTAUTHORIZED|사용자가이 작업을 수행할 수 없습니다.|  
|SCC_E_PROJNOTOPEN|프로젝트 소스 제어에서 열리지 않았습니다.|  
|SCC_I_OPERATIONCANCELED|작업이 완료 되기 전에 취소 되었습니다.|  
  
## <a name="remarks"></a>설명  
 이 작업이 끝나면는 `SCC_STATUS_CHECKEDOUT` 및 `SCC_STATUS_MODIFIED` 플래그는 모두 지워집니다 체크 아웃을 취소 수행 된 파일에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)