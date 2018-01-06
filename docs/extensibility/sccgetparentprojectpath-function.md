---
title: "SccGetParentProjectPath 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccGetParentProjectPath
helpviewer_keywords: SccGetParentProjectPath function
ms.assetid: 62a71579-36b3-48b9-a1c8-04ab100efa08
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8395d73a48d4c8501ba834b2168b5bcbc8019b8b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="sccgetparentprojectpath-function"></a>SccGetParentProjectPath 함수
이 함수는 지정된 된 프로젝트의 부모 프로젝트 경로 확인합니다. 이 함수는 사용자가 Visual Studio 프로젝트를 소스 제어에 추가할 때 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccGetParentProjectPath(  
   LPVOID pContext,  
   HWND   hWnd,  
   LPSTR  lpUser,  
   LPCSTR lpProjPath,  
   LPSTR  lpAuxProjPath,  
   LPSTR  lpParentProjPath  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pContext  
 [in] 소스 제어 플러그 인 컨텍스트 포인터입니다.  
  
 hWnd  
 [in] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에를 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 lpUser  
 [out에서] NULL 종결자를 포함 하 여 SCC_USER_SIZE) (최대 사용자 이름입니다.  
  
 lpProjPath  
 [in] NULL 종결자를 포함 하 여 SCC_PRJPATH_SIZE) (최대 프로젝트 경로 식별 하는 문자열입니다.  
  
 lpAuxProjPath  
 [out에서] NULL 종결자를 포함 하 여 SCC_PRJPATH_SIZE) (최대 프로젝트를 식별 하는 보조 문자열입니다.  
  
 lpParentProjPath  
 [out에서] NULL 종결자를 포함 하 여 SCC_PRJPATH_SIZE) (최대 부모 프로젝트 경로 식별 하는 출력 문자열입니다.  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|부모 프로젝트 경로 가져왔습니다.|  
|SCC_E_INITIALIZEFAILED|프로젝트를 초기화할 수 없습니다.|  
|SCC_E_INVALIDUSER|사용자의 소스 제어 플러그 인에 로그인 하지 못했습니다.|  
|SCC_E_UNKNOWNPROJECT|프로젝트 소스 제어 플러그 인에 인식 되지 않습니다.|  
|SCC_E_INVALIDFILEPATH|잘못 되었거나 사용할 수 없는 파일 경로입니다.|  
|SCC_E_NOTAUTHORIZED|사용자가이 작업을 수행할 수 없습니다.|  
|SCC_E_ACCESSFAILURE|소스 제어 시스템에 네트워크 또는 경합 문제 때문에 액세스 하는 문제가 발생 했습니다. 다시 시도 하 여 것이 좋습니다.|  
|SCC_E_PROJSYNTAXERR|잘못 된 프로젝트 구문입니다.|  
|SCC_E_CONNECTIONFAILURE|연결 문제를 저장 합니다.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|알 수 없는 오류가 발생 했습니다.|  
  
## <a name="remarks"></a>설명  
 이 함수 성공 또는 실패 코드를 반환 하 고, 성공 하는 경우 작성 변수 `lpParentProjPath` 지정된 된 프로젝트에 전체 프로젝트 경로 사용 합니다.  
  
 이 함수는 기존 프로젝트의 프로젝트 경로 부모를 반환합니다. 루트 프로젝트에 대 한 함수에 전달 된 프로젝트 경로 반환 (합니다 즉, 동일한 루트 프로젝트 경로). 프로젝트 경로 소스 제어 플러그 인에 의미 있는 문자열 임을 확인 합니다.  
  
 IDE가 변경 내용을 받아들일 준비가 `lpUser` 및 `lpAuxProjPath` 도 매개 변수입니다. 이러한 문자열 영구적으로 보존 되며 전달할 IDE는 [SccOpenProject](../extensibility/sccopenproject-function.md) 를 열 때이 프로젝트 나중에 있습니다. 따라서 이들이 문자열을 소스 제어 플러그 인을 프로젝트에 연결 하는 데 필요한 추적 정보는 방법을 제공 합니다.  
  
 이 함수는 비슷합니다는 [SccGetProjPath](../extensibility/sccgetprojpath-function.md)제외 하 고 프로젝트를 선택 하려면 사용자는 표시 되지 않습니다. 되지를 기존 프로젝트와만 작동 하지만 새 프로젝트를 만듭니다.  
  
 때 `SccGetParentProjectPath` 호출 `lpProjPath` 및 `lpAuxProjPath` 비워 둘 수 없으며 유효한 프로젝트에 해당 됩니다. 이러한 문자열에 대 한 이전 호출에서 IDE에서 받은 일반적으로 `SccGetProjPath` 함수입니다.  
  
 `lpUser` 인수는 사용자 이름입니다. IDE에서 이전에 수신한 것 같은 사용자 이름을 전달 합니다는 `SccGetProjPath` 함수와 소스 제어 플러그 인 이름을 기본적으로 사용 해야 합니다. 사용자가 이미 열려 있는 연결 플러그 인을 하는 경우 플러그 인은 시도 함수를 자동으로 작동 하는지 확인 하는 모든 프롬프트를 제거 합니다. 그러나 로그인에 실패 하면 플러그 인에서 메시지를 표시 하는 사용자는 로그인에 대 한, 한 유효한 로그인 이름에 다시 전달 받을 때 `lpUser`합니다. IDE는 크기의 버퍼를 할당할 항상 플러그 인이 문자열 변경 될 수 있습니다, 때문에 (`SCC_USER_LEN`+ 1). 문자열이 변경 된 경우 새 문자열에 유효한 로그인 이름이 (적어도 기존 문자열 유효함) 이어야 합니다.  
  
## <a name="technical-notes-for-scccreatesubproject-and-sccgetparentprojectpath"></a>SccCreateSubProject 및 SccGetParentProjectPath에 대 한 기술 참고 사항  
 소스 제어에 솔루션 및 프로젝트 추가 사용자는 소스 제어 시스템에서 위치를 선택 하 라는 메시지가 표시 되는 횟수를 최소화 하기 위해 Visual Studio에서 간소화 되었습니다. 소스 제어 플러그 인 새 함수는 모두를 지 원하는 경우 이러한 변경 내용은 Visual Studio로 활성화 되 고 [SccCreateSubProject](../extensibility/scccreatesubproject-function.md) 및 `SccGetParentProjectPath` 함수입니다. 그러나 이러한 변경 내용을 사용 하지 않도록 설정 하 여 이전 Visual Studio (소스 제어 플러그 인 API 버전 1.1) 동작으로 되돌리려면 다음 레지스트리 항목을 사용할 수 있습니다.  
  
 [HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl] "DoNotCreateSolutionRootFolderInSourceControl" = dword: 00000001  
  
 이 레지스트리 항목이 존재 하지 않거나 dword: 00000000으로 설정 되어, 하는 경우 Visual Studio는 새 함수를 사용 하려고 시도 `SccCreateSubProject`및`SccGetParentProjectPath`합니다.  
  
 레지스트리 항목 dword: 00000001로 설정 되 면 Visual Studio는 이러한 새 함수를 사용 하지 및 소스 제어에 추가 하는 작업은 이전 버전의 Visual Studio에서와 마찬가지로 작동 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccCreateSubProject](../extensibility/scccreatesubproject-function.md)   
 [SccGetProjPath](../extensibility/sccgetprojpath-function.md)