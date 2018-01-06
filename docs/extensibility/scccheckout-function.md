---
title: "SccCheckout 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccCheckout
helpviewer_keywords: SccCheckout function
ms.assetid: 06e9ecd7-fc09-40c1-9dd1-2b56c622c80b
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: af8aac642ecd21f8f4709874e4e3e6ff0b3e58b5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="scccheckout-function"></a>SccCheckout 함수
정규화 된 파일 이름의 목록을 지정 된 경우이 함수 확인 로컬 드라이브에 있습니다. 체크 아웃 되 고 모든 파일에 주석을 적용 됩니다. 주석 인수 수는 `null` 문자열입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccCheckout (  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LPCSTR    lpComment,  
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
 [in] 체크 아웃 하도록 선택한 파일 수입니다.  
  
 lpFileNames  
 [in] 파일을 체크 아웃의 정규화 된 로컬 경로 이름 배열입니다.  
  
 lpComment  
 [in] 각 체크 아웃 되 고 선택한 파일에 적용할 설명입니다.  
  
 fOptions  
 [in] 명령 플래그 (참조 [에서 특정 명령을 사용 하는 비트](../extensibility/bitflags-used-by-specific-commands.md)).  
  
 pvOptions  
 [in] 소스 제어 플러그 인에 대 한 옵션입니다.  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|체크 아웃 했습니다.|  
|SCC_E_FILENOTCONTROLLED|선택한 파일은 소스 코드 제어 하지 않습니다.|  
|SCC_E_ACCESSFAILURE|소스 제어 시스템에 네트워크 또는 경합 문제 때문에 액세스 하는 문제가 발생 했습니다. 다시 시도 하 여 것이 좋습니다.|  
|SCC_E_NOTAUTHORIZED|사용자가이 작업을 수행할 수 없습니다.|  
|SCC_E_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다. 파일 체크 아웃 되지 않았습니다.|  
|SCC_E_ALREADYCHECKEDOUT|사용자가 이미 파일을 체크 아웃 합니다.|  
|SCC_E_FILEISLOCKED|새 버전 생성 등의 금지 된 파일이 잠겨 있습니다.|  
|SCC_E_FILEOUTEXCLUSIVE|다른 사용자는이 파일에 대 한 단독 체크 아웃을 종료 했습니다.|  
|SCC_I_OPERATIONCANCELED|작업이 완료 되기 전에 취소 되었습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [특정 명령에 사용되는 Bitflag](../extensibility/bitflags-used-by-specific-commands.md)