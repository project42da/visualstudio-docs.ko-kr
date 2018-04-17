---
title: SccDirDiff 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccDirDiff
helpviewer_keywords:
- SccDirDiff function
ms.assetid: 26c9ba92-e3b9-4dd2-bd5e-76b17745e308
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7d2bea7816375da1131f557ebcbe206056f347f2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="sccdirdiff-function"></a>SccDirDiff 함수
이 함수는 클라이언트 디스크에서 현재 로컬 디렉터리와 해당 소스 제어에서 프로젝트 간의 차이 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccDirDiff(  
   LPVOID    pContext,  
   HWND      hWnd,  
   LPCSTR    lpDirName,  
   LONG      dwFlags,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pContext  
 [in] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 hWnd  
 [in] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에를 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 lpDirName  
 [in] 정규화 된 경로 표시할 시각적 차이점에 대 한 로컬 디렉터리입니다.  
  
 dwFlags  
 [in] 명령 플래그 (설명 참조 섹션).  
  
 pvOptions  
 [in] 소스 제어 플러그 인에 대 한 옵션입니다.  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|디스크에 있는 디렉터리에서 소스 코드 제어 프로젝트와 같습니다.|  
|SCC_I_FILESDIFFER|디스크에 있는 디렉터리는 소스 코드 제어에서 프로젝트와에서 다릅니다.|  
|SCC_I_RELOADFILE|파일 또는 프로젝트 다시 로드 해야 합니다.|  
|SCC_E_FILENOTCONTROLLED|디렉터리가 소스 코드 제어 하지 않습니다.|  
|SCC_E_NOTAUTHORIZED|사용자가이 작업을 수행할 수 없습니다.|  
|SCC_E_ACCESSFAILURE|소스 제어 시스템에 네트워크 또는 경합 문제 때문에 액세스 하는 문제가 발생 했습니다. 다시 시도 하 여 것이 좋습니다.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|알 수 없는 오류가 발생 했습니다.|  
|SCC_E_FILENOTEXIST|로컬 디렉터리를 찾을 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 이 함수에 대 한 사용자에 게 지정된 된 디렉터리에 대 한 변경의 목록을 표시 하려면 플러그 인 소스 제어 명령에 사용 됩니다. 플러그 인 디스크에는 사용자의 디렉터리와 버전 제어에서 해당 프로젝트 간의 차이 표시 하려면 선택한 형식으로 별도 창을 엽니다.  
  
 경우 모두에서 디렉터리의 플러그인 지원 비교, "빠른 비교" 옵션 지원 되지 않는 경우에 비교 디렉터리의 파일 이름으로 지원 해야 합니다.  
  
|`dwFlags`|해석|  
|---------------|--------------------|  
|SCC_DIFF_IGNORECASE|대/소문자 구분 비교 (diff 빠른 또는 시각적 개체 중 하나에 대 한 사용할 수 있음).|  
|SCC_DIFF_IGNORESPACE|공백 (빠른 diff 또는 시각적 개체 중 하나에 대해 사용할 수 있음)를 무시 합니다.|  
|SCC_DIFF_QD_CONTENTS|소스 제어 플러그 인에서 지 원하는, 자동으로 디렉터리를 바이트 단위로 비교 합니다.|  
|SCC_DIFF_QD_CHECKSUM|플러그 인에서 지 원하는, 자동으로 체크섬을 통해 디렉터리를 비교 하거나, 지원 되지 않는 경우 SCC_DIFF_QD_CONTENTS로 대체 합니다.|  
|SCC_DIFF_QD_TIME|플러그 인에서 지 원하는, 자동으로 타임 스탬프로 통해 디렉터리를 비교 하거나, 지원 되지 않는 경우 대체 SCC_DIFF_QD_CHECKSUM 또는 SCC_DIFF_QD_CONTENTS 합니다.|  
  
> [!NOTE]
>  이 함수를 사용으로 동일한 명령 플래그는 [SccDiff](../extensibility/sccdiff-function.md)합니다. 그러나 소스 제어 플러그 인 디렉터리에 대 한 "빠른 비교" 작업을 지원 하지 않도록 선택할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)