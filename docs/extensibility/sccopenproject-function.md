---
title: SccOpenProject 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccOpenProject
helpviewer_keywords:
- SccOpenProject function
ms.assetid: d609510b-660a-46d7-b93d-2406df20434d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 15d9cf6d5fa4533b5ee0ff65f8aeae86df3d571a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="sccopenproject-function"></a>SccOpenProject 함수
이 함수는 기존 소스 제어 프로젝트를 열거나 새를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccOpenProject (  
   LPVOID        pvContext,  
   HWND          hWnd,  
   LPSTR         lpUser,  
   LPCSTR        lpProjName,  
   LPCSTR        lpLocalProjPath,  
   LPSTR         lpAuxProjPath,  
   LPCSTR        lpComment,  
   LPTEXTOUTPROC lpTextOutProc,  
   LONG          dwFlags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pvContext  
 [in] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 hWnd  
 [in] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에를 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 lpUser  
 [out에서] \(NULL 종결자를 포함 하 여 SCC_USER_SIZE 초과 하지 않음) 하는 사용자의 이름입니다.  
  
 lpProjName  
 [in] 프로젝트의 이름을 나타내는 문자열입니다.  
  
 lpLocalProjPath  
 [in] 경로 프로젝트에 대 한 작업 폴더입니다.  
  
 lpAuxProjPath  
 [out에서] 프로젝트 (NULL 종결자를 포함 하 여 SCC_AUXPATH_SIZE 초과 하지 않음)를 식별 하는 선택적 보조 문자열입니다.  
  
 lpComment  
 [in] 생성 중인 새 프로젝트를 주석 처리 합니다.  
  
 lpTextOutProc  
 [in] 소스 제어 플러그 인에서 출력 텍스트를 표시 하는 선택적 콜백 함수입니다.  
  
 dwFlags  
 [in] 신호를 프로젝트를 소스에 알 수 없는 경우 새 프로젝트를 만들어야 하는지 여부를 제어 플러그 인 합니다. 값의 조합 수 `SCC_OP_CREATEIFNEW` 및 `SCC_OP_SILENTOPEN.`  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|프로젝트 열기에서 성공 합니다.|  
|SCC_E_INITIALIZEFAILED|프로젝트를 초기화할 수 없습니다.|  
|SCC_E_INVALIDUSER|사용자 소스 제어 시스템에 로그인 하지 못했습니다.|  
|SCC_E_COULDNOTCREATEPROJECT|프로젝트; 호출 전에 없었습니다.  `SCC_OPT_CREATEIFNEW` 플래그가 설정 되었지만 프로젝트를 만들 수 없습니다.|  
|SCC_E_PROJSYNTAXERR|잘못 된 프로젝트 구문입니다.|  
|SCC_E_UNKNOWNPROJECT|프로젝트를 소스 제어 플러그 인을 알 수 없는 및 `SCC_OPT_CREATEIFNEW` 플래그가 설정 되지 않았습니다.|  
|SCC_E_INVALIDFILEPATH|잘못 되었거나 사용할 수 없는 파일 경로입니다.|  
|SCC_E_NOTAUTHORIZED|사용자가이 작업을 수행할 수 없습니다.|  
|SCC_E_ACCESSFAILURE|소스 제어 시스템에 네트워크 또는 경합 문제 때문에 액세스 하는 문제가 발생 했습니다. 다시 시도 하 여 것이 좋습니다.|  
|SCC_E_NONSPECFICERROR|알 수 없는 오류입니다. 소스 제어 시스템을 초기화 하지 못했습니다.|  
  
## <a name="remarks"></a>설명  
 IDE 사용자 이름에 전달할 수 있습니다 (`lpUser`), 있고 단순히 빈 문자열에 대 한 포인터에 전달할 수 있습니다. 사용자 이름이 없는 경우 소스 제어 플러그 인을 기본값으로 사용 해야 합니다. 그러나 이름이 전달 된 또는 지정 된 이름의 로그인에 실패 하는 경우 플러그 인 사용자가 로그인 메시지를 표시 하 고에 유효한 이름을 반환 하는 `lpUser` 유효한 로그인을 받을 때`.` 플러그 인는 사용자 이름 문자열로 변경 될 수 있으므로 IDE에서 항상 크기의 버퍼를 할당 합니다 (`SCC_USER_LEN`+ 1 또는 null 종결자를 위한 공간이 포함 된 SCC_USER_SIZE).  
  
> [!NOTE]
>  IDE를 수행 해야 할 수는 첫 번째 작업에 대 한 호출 수는 `SccOpenProject` 함수 또는 [SccGetProjPath](../extensibility/sccgetprojpath-function.md)합니다. 이러한 이유로 그중에서 둘 다 동일한 `lpUser` 매개 변수입니다.  
  
 `lpAuxProjPath` 및`lpProjName` 솔루션 파일에서 읽은 또는 호출에서 반환 되는 `SccGetProjPath` 함수입니다. 이러한 매개 변수 소스 제어 플러그 인은 프로젝트와 연결 하는 문자열을 포함 하며는 플러그 인에 의미를 갖습니다. 해당 문자열이 없거나 솔루션 파일에 있고 사용자가 찾아보려면 묻지 (통해 문자열을 반환 하는 `SccGetProjPath` 함수), 모두에 대 한 빈 문자열을 전달 하는 IDE `lpAuxProjPath` 및 `lpProjName`, 이러한 값을 업데이트할 수 예상 플러그 인 경우가이 함수를 반환합니다.  
  
 `lpTextOutProc` 명령 결과 출력을 표시 하기 위해 플러그 인 소스 제어에 IDE에서 제공 하는 콜백 함수에 포인터가입니다. 이 콜백 함수에 자세히 설명 되어 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)합니다.  
  
> [!NOTE]
>  소스 제어 플러그 인이 활용 하기 위해 노드가, 하는 경우 설정 있어야 합니다는 `SCC_CAP_TEXTOUT` 플래그는 [SccInitialize](../extensibility/sccinitialize-function.md)합니다. 해당 플래그 설정 되지 않은 경우 또는 IDE에이 기능을 지원 하지 않는 경우 `lpTextOutProc` 됩니다 `NULL`합니다.  
  
 `dwFlags` 매개 변수에서 열려는 프로젝트가 현재 존재 하지 않는 결과 제어 합니다. 두 비트 이루어져 `SCC_OP_CREATEIFNEW` 및 `SCC_OP_SILENTOPEN`합니다. 프로젝트가 이미 열려 있으면 함수 단순히 프로젝트를 열고 반환 `SCC_OK`합니다. 프로젝트가 존재 하지 않는 경우는 `SCC_OP_CREATEIFNEW` 플래그의 on, 소스 제어 플러그 인 수 프로젝트 소스 제어 시스템에서 만들고, 열고, 반환 `SCC_OK`합니다. 프로젝트가 존재 하지 않는 경우는 `SCC_OP_CREATEIFNEW` 플래그가 해제 되어 있으면 도구 플러그 인은 확인 한 후의 `SCC_OP_SILENTOPEN` 플래그입니다. 해당 플래그를 없는 경우에 플러그 인 경우도 있습니다 프로젝트 이름에 대 한 사용자. 해당 플래그에 있으면, 플러그 인을 반환 하면 `SCC_E_UNKNOWNPROJECT`합니다.  
  
## <a name="calling-order"></a>순서를 호출합니다.  
 이벤트의 정상적인는 [SccInitialize](../extensibility/sccinitialize-function.md) 를 소스 제어 세션을 열려면 먼저 호출 됩니다. 세션 구성에 대 한 호출 될 수 있습니다 `SccOpenProject`뒤에 다른 소스 제어 플러그 인 API 함수 호출, 및을 호출 하 여 종료 됩니다는 [SccCloseProject](../extensibility/scccloseproject-function.md)합니다. 이러한 세션을 여러 번 반복 될 수 있습니다는 [SccUninitialize](../extensibility/sccuninitialize-function.md) 호출 됩니다.  
  
 소스 제어 플러그 인 설정 하는 경우는 `SCC_CAP_REENTRANT` 비트 `SccInitialize`, 다음 위의 세션 시퀀스 동시에 여러 번 반복 될 수 있습니다. 다른 `pvContext` 구조는 서로 다른 세션의 각 추적 `pvContext` 한 번에 하나의 열려 있는 프로젝트와 연결 됩니다. 에 따라는`pvContext` 매개 변수를 플러그 인 결정할 수 어떤 프로젝트는 특정 한 호출에서 참조 됩니다. 기능 비트 경우 `SCC_CAP_REENTRANT` 을 설정 하지 않으면 nonreentrant 소스 제어 플러그 인 프로젝트를 사용 하는 기능이 제한 됩니다.  
  
> [!NOTE]
>  `SCC_CAP_REENTRANT` 비트 소스 제어 플러그 인 API의 버전 1.1에서에서 도입 되었습니다. 이 설정 되어 있지 않거나 버전 1.0에서는 무시 됩니다 및 모든 버전 1.0 소스 제어 플러그 인 nonreentrant 것으로 간주 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccCloseProject](../extensibility/scccloseproject-function.md)   
 [SccGetProjPath](../extensibility/sccgetprojpath-function.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)   
 [SccUninitialize](../extensibility/sccuninitialize-function.md)   
 [문자열 길이에 대 한 제한](../extensibility/restrictions-on-string-lengths.md)   
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)