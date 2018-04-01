---
title: SccCheckin 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccCheckin
helpviewer_keywords:
- SccCheckin function
ms.assetid: e3f26ac2-6163-42e1-a764-22cfea5a3bc6
caps.latest.revision: 16
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: f95377f79d02952c63b673d50569fac058a8573c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="scccheckin-function"></a>SccCheckin 함수
이 함수를 이전에 체크 아웃 된 파일 변경 내용을 저장 하 고 새 버전을 만드는 소스 제어 시스템을 확인 합니다. 이 함수는 작업 항목 및 체크 인 파일의 이름 배열을 수 함께 호출 되었습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccCheckin (  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPSTR*    lpFileNames,  
   LPCSTR    lpComment,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pvContext  
 [in] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 hWnd  
 [in] 소스 코드 제어 플러그 인을 제공 하는 모든 대화 상자에 대 한 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 nFiles  
 [in] 체크 인 선택한 파일의 수입니다.  
  
 lpFileNames  
 [in] 체크 인 파일의 정규화 된 로컬 경로 이름 배열입니다.  
  
 lpComment  
 [in] 각 체크 인 되 고 선택한 파일에 적용할 설명입니다. 이 `NULL` 메모에 대 한 소스 제어 플러그 인에서 메시지를 표시 하는 경우.  
  
 fOptions  
 [in] 명령 플래그, 0 또는 `SCC_KEEP_CHECKEDOUT`합니다.  
  
 pvOptions  
 [in] SCC 플러그 인에 대 한 옵션입니다.  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|파일이는 성공적으로 체크 인 되었습니다.|  
|SCC_E_FILENOTCONTROLLED|선택한 파일은 소스 코드 제어 하지 않습니다.|  
|SCC_E_ACCESSFAILURE|소스 제어 시스템에 네트워크 또는 경합 문제 때문에 액세스 하는 문제가 발생 했습니다. 다시 시도 하 여 것이 좋습니다.|  
|SCC_E_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다. 파일 체크 인 되었습니다.|  
|SCC_E_NOTCHECKEDOUT|사용자가 하지 파일을 체크 아웃을 체크 인할 수 없습니다.|  
|SCC_E_CHECKINCONFLICT|때문에 체크 인을 수행할 수 없습니다.<br /><br /> -다른 사용자가 체크 인 계속 및 `bAutoReconcile` false입니다.<br /><br /> 또는<br /><br /> (예를 들어 경우 파일은 이진)-자동 병합을 수행할 수 없습니다.|  
|SCC_E_VERIFYMERGE|파일 자동 병합 되었지만 사용자가 확인 보류 중인 검사 하지 않았습니다.|  
|SCC_E_FIXMERGE|파일 자동 병합 되었지만 인해 병합 충돌이 수동으로 해결 해야 하는 검사 하지 않았습니다.|  
|SCC_E_NOTAUTHORIZED|사용자가이 작업을 수행할 수 없습니다.|  
|SCC_I_OPERATIONCANCELED|작업이 완료 되기 전에 취소 되었습니다.|  
|SCC_I_RELOADFILE|파일 또는 프로젝트 다시 로드 해야 합니다.|  
|SCC_E_FILENOTEXIST|로컬 파일을 찾을 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 체크 인 모든 파일에 주석을 적용 됩니다. 주석 인수 수는 `null` 문자열, 소스 제어 플러그 인이 경우 각 파일에 대 한 설명 문자열에 대 한 사용자를 표시할 수 있습니다.  
  
 `fOptions` 인수 값을 지정할 수는 `SCC_KEEP_CHECKEDOUT` 파일을 확인 하 고 다시 체크 아웃 하는 사용자의 의도 나타내는 플래그입니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)