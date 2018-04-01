---
title: SccGetEvents 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccGetEvents
helpviewer_keywords:
- SccGetEvents function
ms.assetid: 32f8147d-6dcc-465e-b07b-42da5824f9b0
caps.latest.revision: 13
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e2e9a22d0340774087fab8dd7dc564f415d9d9aa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="sccgetevents-function"></a>SccGetEvents 함수
이 함수는 큐에 대기 중인된 상태 이벤트를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccGetEvents (  
   LPVOID pvContext,  
   LPSTR  lpFileName,  
   LPLONG lpStatus,  
   LPLONG pnEventsRemaining  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pvContext  
 [in] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 lpFileName  
 [out에서] 소스 제어 플러그 인 반환된 된 파일 이름 (최대 _MAX_PATH 자)를 배치 하는 위치를 버퍼링 합니다.  
  
 lpStatus  
 [out에서] 상태 코드 반환 (참조 [파일 상태 코드](../extensibility/file-status-code-enumerator.md) 가능한 값에 대 한).  
  
 pnEventsRemaining  
 [out에서] 이 호출 후 큐에 남아 있는 항목 수를 반환 합니다. 호출자에 게를 호출할지 결정할 수 있습니다이 수가 큰 경우는 [SccQueryInfo](../extensibility/sccqueryinfo-function.md) 모든 정보를 한 번에를 가져옵니다.  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|성공 하는 이벤트를 가져옵니다.|  
|SCC_E_OPNOTSUPPORTED|이 함수는 지원 되지 않습니다.|  
|SCC_E_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다.|  
  
## <a name="remarks"></a>설명  
 이 함수를 소스 제어에서 파일에 대 한 상태 업데이트 되었는지를 보려면 유휴 처리 동안 호출 됩니다. 소스 제어 플러그 인을 알고 있는 모든 파일의 상태를 유지 하 고 변경 될 때마다 상태를 기록 플러그인, 상태 및 연결된 된 파일 큐에 저장 됩니다. 때 `SccGetEvents` 호출 되는 상위 큐의 요소를 검색 하 고 반환 합니다. 이 유일한 이전에 캐시 된 정보를 반환 하는 제한 된 함수와 매우 신속 하 게 처리할 (즉, 없음 디스크의 읽기 또는 상태에 대 한 소스 제어 시스템에 대 한 요청); 있어야 합니다. 그렇지 않으면 IDE의 성능 저하를 시작할 수 있습니다.  
  
 소스 제어 플러그 인 가리키는 버퍼에 빈 문자열을 저장 보고서는 업데이트 되지 상태 이면 `lpFileName`합니다. 이렇게 하지 않으면 플러그 인 보관 파일의 전체 경로 이름 상태 정보가 변경 된 반환 하는 적절 한 상태 코드에 대 한 (에 자세히 설명 하는 값 중 하나 [파일 상태 코드](../extensibility/file-status-code-enumerator.md)).  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [파일 상태 코드](../extensibility/file-status-code-enumerator.md)