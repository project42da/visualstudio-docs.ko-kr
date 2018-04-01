---
title: SccGetProjPath 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccGetProjPath
helpviewer_keywords:
- SccGetProjPath function
ms.assetid: 1079847e-d45f-4cb8-9d92-1e01ce5d08f6
caps.latest.revision: 15
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 2ce41826a3a0d778c5a417496d47f290e97806fb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="sccgetprojpath-function"></a>SccGetProjPath 함수
이 함수에 대 한 소스 제어 플러그 인에 의미 있는 문자열 인 프로젝트 경로 라는 메시지를 표시 합니다. 사용자가 때 호출 됩니다.  
  
-   새 프로젝트 만들기  
  
-   버전 제어에 기존 프로젝트 추가  
  
-   기존 버전 제어 프로젝트를 찾으려고 시도  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccGetProjPath (  
   LPVOID pvContext,  
   HWND   hWnd,  
   LPSTR  lpUser,  
   LPSTR  lpProjName,  
   LPSTR  lpLocalPath,  
   LPSTR  lpAuxProjPath,  
   BOOL   bAllowChangePath,  
   LPBOOL pbNew  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pvContext  
 [in] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 hWnd  
 [in] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에를 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 lpUser  
 [out에서] 사용자 이름 (NULL 종결자를 포함 하 여 SCC_USER_SIZE 초과 하지 않음)  
  
 lpProjName  
 [out에서] IDE 프로젝트, 프로젝트 작업 영역 또는 메이크파일 (NULL 종결자를 포함 하 여 SCC_PRJPATH_SIZE 초과 하지 않음)의 이름입니다.  
  
 lpLocalPath  
 [out에서] 프로젝트의 작업 경로입니다. 경우 `bAllowChangePath` 은 `TRUE`, 소스 제어 플러그 인이 문자열 (null 종결자를 포함 하 여 _MAX_PATH 초과 하지 않음)을 수정할 수 있습니다.  
  
 lpAuxProjPath  
 [out에서] 반환 된 프로젝트 경로 (NULL 종결자를 포함 하 여 SCC_PRJPATH_SIZE 초과 하지 않음)에 대 한 버퍼입니다.  
  
 bAllowChangePath  
 [in] 이것이 `TRUE`, 소스 제어 플러그 인에 대 한 메시지를 표시 하 고 수정할 수는 `lpLocalPath` 문자열입니다.  
  
 pbNew  
 [out에서] 값에 방문 하 고 새 프로젝트를 만들 것인지를 나타냅니다. 반환 된 값에는 프로젝트를 만드는 성공 했음을 의미 합니다.  
  
|들어오는|해석|  
|--------------|--------------------|  
|true|사용자는 새 프로젝트를 만들 수 있습니다.|  
|false|사용자는 새 프로젝트를 만들 수 없습니다.|  
  
|나가는 포트|해석|  
|--------------|--------------------|  
|true|새 프로젝트를 만들었습니다.|  
|false|기존 프로젝트를 선택 했습니다.|  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|프로젝트를 마지막 성공적으로 생성 하거나 검색 합니다.|  
|SCC_I_OPERATIONCANCELED|작업이 취소 되었습니다.|  
|SCC_E_ACCESSFAILURE|소스 제어 시스템에 네트워크 또는 경합 문제 때문에 액세스 하는 문제가 발생 했습니다.|  
|SCC_E_CONNECTIONFAILURE|소스 제어 시스템에 연결 하려는 중 오류가 발생 했습니다.|  
|SCC_E_NONSPECIFICERROR|지정되지 않은 오류가 발생했습니다.|  
  
## <a name="remarks"></a>설명  
 이 함수의 용도 매개 변수를 얻으려고 IDE `lpProjName` 및 `lpAuxProjPath`합니다. 소스 제어 플러그 인 사용자에 게이 정보를 요청 후 IDE에 이러한 두 문자열을 전달 합니다. IDE의 솔루션 파일에 이러한 문자열을 지속 하 고 파이프라인 연산자는 [SccOpenProject](../extensibility/sccopenproject-function.md) 사용자가이 프로젝트를 열 때마다 합니다. 이러한 문자열은 프로젝트와 관련 된 정보를 추적 플러그 인을 사용 합니다.  
  
 함수를 처음 호출할 때는 `lpAuxProjPath` 빈 문자열로 설정 됩니다. `lProjName`또한 비어 있을 수 소스 제어 플러그 인 사용 하거나 무시할 수 있는 IDE 프로젝트 이름을 포함할 수 있습니다. 함수는 성공적으로 반환 될 때 해당 문자열 두 플러그 인 반환 합니다. IDE 이러한 문자열에 대 한가 정도 하지 않습니다, 사용 하지 않으며 사용자 이미지를 수정할 수 없도록 합니다. 사용자가 설정을 변경 하려는 경우 IDE는 호출 `SccGetProjPath` 다시 같은 값의 전달 받았습니다 이전 시간입니다. 이 플러그 인 완전히 제어할 이러한 두 문자열을 제공합니다.  
  
 에 대 한 `lpUser`, IDE 사용자 이름에 전달할 수 있습니다 또는 단순히 빈 문자열에 대 한 포인터에 통과할 수 있습니다. 사용자 이름이 없는 경우 소스 제어 플러그 인을 기본값으로 사용 해야 합니다. 그러나 이름이 전달 되지 않은 경우 또는 지정 된 이름의 로그인에 실패 하는 경우 플러그 인에서 메시지를 표시 한 로그인 및 이름에 다시 전달에 대 한 사용자 `lpUser` 유효한 로그인을 받을 때입니다. IDE는 크기의 버퍼를 할당할 항상 플러그 인이 문자열 변경 될 수 있습니다, 때문에 (`SCC_USER_LEN`+ 1).  
  
> [!NOTE]
>  IDE를 수행 하는 첫 번째 작업에 대 한 호출 수는 `SccOpenProject` 함수 또는 `SccGetProjPath` 함수입니다. 둘 모두 이미 동일한 `lpUser` 소스 제어 플러그 타임에 사용자를 로그인 할 수 있는 매개 변수입니다. 함수에서 반환 된 값이 실패 했음을 의미, 경우에 플러그 인 채워야 유효한 로그인 이름으로이 문자열.  
  
 `lpLocalPath`사용자는 프로젝트를 유지 하는 위치는 디렉터리가입니다. 빈 문자열일 수 있습니다. (의 경우 처럼를 소스 제어 시스템에서 프로젝트를 다운로드 하 사용자) 현재 정의 된 디렉터리가 없는 한 경우 `bAllowChangePath` 은 `TRUE`, 소스 제어 플러그 인 입력에 대 한 사용자 수 또는 일부 다른 메서드를 사용 하 여 해당 문자열을 소유 `lpLocalPath`합니다. 경우 `bAllowChangePath` 은 `FALSE`, 플러그 인 변경 안 문자열, 사용자가 이미 지정된 된 디렉터리에서 작업 하기 때문에 있습니다.  
  
 사용자를 소스 제어 설정 해야 새 프로젝트를 만드는 경우 소스 제어 플러그 인 만들지 못할 수도 있습니다 실제로 해당 소스 제어 시스템에서 시간에 `SccGetProjPath` 호출 됩니다. 그 대신, 전달 다시에 0이 아닌 값이 있는 함께 문자열 `pbNew`, 소스 제어 시스템에서 프로젝트를 만들 수는 나타내는입니다.  
  
 예를 들어 사용자에는 **새 프로젝트** Visual Studio에서 마법사가 자신의 프로젝트를 소스 제어에 추가 하 고이 함수를 호출 하는 Visual Studio 플러그 인에 소스 제어 시스템에서 새 프로젝트를 만들려면 해도 되는지 결정 Visual Studio 프로젝트를 포함 합니다. 사용자가 클릭할 경우 **취소** 마법사를 완료 하기 전에 프로젝트 만들어지지 않습니다. 사용자가 클릭할 경우 **확인**, Visual Studio에서 호출 `SccOpenProject`을 전달 `SCC_OPT_CREATEIFNEW`, 소스 제어 프로젝트는 해당 시점에 생성 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)