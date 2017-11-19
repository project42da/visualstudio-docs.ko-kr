---
title: "SccDiff 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccDiff
helpviewer_keywords: SccDiff function
ms.assetid: d49bc8c5-f631-4153-9d3c-feb3564da305
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0bfe7da717a59b114052080048e97b1d6fcdd425
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="sccdiff-function"></a>SccDiff 함수
이 함수 표시 (또는 필요에 따라 확인에 대 한) 원본에는 로컬 디스크에 현재 파일과 해당 마지막 체크 인 버전 간의 차이점 제어 시스템입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccDiff(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LPCSTR    lpFileName,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pvContext  
 [in] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 hWnd  
 [in] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에를 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 lpFileName  
 [in] 차이 요청한 대상 파일 이름입니다.  
  
 fOptions  
 [in] 명령 플래그입니다. 자세한 내용은 설명 부분을 참조 하십시오.  
  
 pvOptions  
 [in] 소스 제어 플러그 인에 대 한 옵션입니다.  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|작업 복사본 및 서버 버전은 동일 합니다.|  
|SCC_I_FILESDIFFERS|작업 복사본이 소스 제어에서 사용 중인 버전에서 다릅니다.|  
|SCC_I_RELOADFILE|파일 또는 프로젝트 다시 로드 해야 합니다.|  
|SCC_E_FILENOTCONTROLLED|소스 제어에서 파일이 아닙니다.|  
|SCC_E_NOTAUTHORIZED|사용자가이 작업을 수행할 수 없습니다.|  
|SCC_E_ACCESSFAILURE|소스 제어 시스템에 네트워크 또는 경합 문제 때문에 액세스 하는 문제가 발생 했습니다. 다시 시도 하 여 것이 좋습니다.|  
|SCC_E_NONSPECIFICERROR|알 수 없는 오류입니다. 파일의 차이점을 가져오지 않았습니다.|  
|SCC_E_FILENOTEXIST|로컬 파일을 찾을 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 이 함수는 두 가지 다른 목적을 지원합니다. 기본적으로 파일에 변경 내용 목록을 표시합니다. 소스 제어 플러그 인 디스크에 대 한 사용자의 파일 및 소스 제어에서 파일의 최신 버전 간 차이점을 선택 하는 모든 형식에 별도 창을 엽니다.  
  
 또는 IDE 단순히 파일 변경 되었는지 여부를 확인 해야 합니다. 예를 들어 IDE는 파일을 체크 아웃 한 사용자에 게 알리지 않고 안전 하 게 보호 되는지 확인 해야 합니다. IDE에서 전달 하는 경우에 `SCC_DIFF_CONTENTS` 플래그입니다. 소스 제어 플러그 인 소스 제어 파일에 대해 바이트 단위로 디스크에 파일을 확인 하 고 두 파일은 사용자에 게 아무것도 표시 하지 않고 다른 지 여부를 나타내는 값을 반환 해야 합니다.  
  
 소스 제어 플러그 인 한 성능 최적화로 체크섬 또는 호출한에 대 한 바이트 단위로 비교 하는 대신 타임 스탬프를 기반으로 하는 대신 사용할 수 있습니다 `SCC_DIFF_CONTENTS`: 분명히 빨라지지만 불안정할 이러한 형태의 비교 됩니다. 모든 소스 제어 시스템에는 이러한 대체 비교 메서드를 지원할 수 있습니다 하며 플러그 인 대체 내용 비교 있을 수 있습니다. 모든 소스 제어 플러그 인을 여기에 최소한 지원 해야 내용을 비교 합니다.  
  
> [!NOTE]
>  빠른 차이 플래그는 함께 사용할 수 없습니다. 없음 플래그를 전달 하는 유효 하지만 동시에 여러 개 전달할 올바르지 않습니다. `SCC_DIFF_QUICK_DIFF`모든 플래그를 결합 하는 마스크는 데 사용할 수를 테스트 하지만 매개 변수로 전달 되지 해야 합니다.  
  
|`fOption`|의미|  
|---------------|-------------|  
|SCC_DIFF_IGNORECASE|대/소문자 구분 비교 (빠른 또는 시각적 차이점에 대해 사용할 수 있음).|  
|SCC_DIFF_IGNORESPACE|공백 (빠른 또는 시각적 차이점에 대해 사용할 수 있음)를 무시 합니다.|  
|SCC_DIFF_QD_CONTENTS|자동으로 파일을 바이트 단위로 비교합니다.|  
|SCC_DIFF_QD_CHECKSUM|지원 되는 경우 체크섬을 통해 파일을 자동으로 비교 합니다. 지원 되지 않는 경우 대신 내용 비교 합니다.|  
|SCC_DIFF_QD_TIME|지원 되는 경우 해당 타임 스탬프를 통해 파일을 자동으로 비교 합니다. 지원 되지 않는 경우 대신 내용 비교 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)