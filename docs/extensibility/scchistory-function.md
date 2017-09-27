---
title: "SccHistory 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccHistory
helpviewer_keywords:
- SccHistory function
ms.assetid: a636d9d3-47c1-4b48-ac6b-bcfde19d6cf9
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 0efb8505fa59957f8178214d64c7ac0d979a3359
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="scchistory-function"></a>SccHistory 함수
이 함수에는 지정 된 파일의 기록을 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccHistory(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pvContext`  
 [in] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 `hWnd`  
 [in] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에를 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 `nFiles`  
 [in] 에 지정 된 파일의 수는 `lpFileName` 배열입니다.  
  
 `lpFileName`  
 [in] 파일의 정규화 된 이름의 배열입니다.  
  
 `fOptions`  
 [in] 명령 플래그 (현재 사용 되지 않음)입니다.  
  
 `pvOptions`  
 [in] 소스 제어 플러그 인에 대 한 옵션입니다.  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|버전 기록 성공적으로 가져온 것입니다.|  
|SCC_I_RELOADFILE|소스 제어 시스템 (예를 들어, 이전 버전을 가져오는)에서 기록을 인출 하는 동안 디스크에 있는 파일을 실제로 수정 하므로 IDE이이 파일을 다시 로드 해야 합니다.|  
|SCC_E_FILENOTCONTROLLED|소스 제어에서 파일이 아닙니다.|  
|SCC_E_OPNOTSUPPORTED|소스 제어 시스템에서이 작업을 지원 하지 않습니다.|  
|SCC_E_NOTAUTHORIZED|사용자가이 작업을 수행할 수 없습니다.|  
|SCC_E_ACCESSFAILURE|소스 제어 시스템에 네트워크 또는 경합 문제 때문에 액세스 하는 문제가 발생 했습니다. 다시 시도 하 여 것이 좋습니다.|  
|SCC_E_PROJNOTOPEN|프로젝트 되어 열립니다.|  
|SCC_E_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다. 파일 히스토리를 가져올 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 소스 제어 플러그 인 각 파일의 기록을 표시 하는 자체 대화 상자를 표시할 수를 사용 하 여 `hWnd` 부모 창으로 합니다. 또는 선택적 텍스트 출력 콜백 함수에 제공 되는 [SccOpenProject](../extensibility/sccopenproject-function.md) 지 원하는 경우 사용할 수 있습니다.  
  
 참고가 특정 상황에서는이 호출을 실행 하는 동안 검사할 파일이 변경 될 수 있습니다. 예를 들어는 [!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)] 기록 명령은 사용자 파일의 이전 버전을 얻으려면 기회를 제공 합니다. 이 경우 소스 제어 플러그 인 반환 `SCC_I_RELOAD` 경고 IDE 파일 다시 로드 해야 합니다.  
  
> [!NOTE]
>  소스 제어 플러그 인 파일의 배열에 대해이 함수를 지원 하지 않으면, 첫 번째 파일에 대 한 파일 히스토리만 표시할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)
