---
title: "SccGetParentProjectPath 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccGetParentProjectPath"
helpviewer_keywords: 
  - "SccGetParentProjectPath 함수"
ms.assetid: 62a71579-36b3-48b9-a1c8-04ab100efa08
caps.latest.revision: 17
caps.handback.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
---
# SccGetParentProjectPath 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 지정된 된 프로젝트의 부모 프로젝트 경로 결정합니다. 이 함수는 사용자가 소스 제어에 Visual Studio 프로젝트를 추가할 때 호출 됩니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccGetParentProjectPath(  
   LPVOID pContext,  
   HWND   hWnd,  
   LPSTR  lpUser,  
   LPCSTR lpProjPath,  
   LPSTR  lpAuxProjPath,  
   LPSTR  lpParentProjPath  
);  
```  
  
#### 매개 변수  
 pContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 포인터입니다.  
  
 hWnd  
 \[in\] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에 대 한 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 lpUser  
 \[에서, out\] NULL 종결자를 포함 하 여 SCC\_USER\_SIZE\) \(최대 사용자 이름입니다.  
  
 lpProjPath  
 \[in\] NULL 종결자를 포함 하 여 SCC\_PRJPATH\_SIZE\) \(최대 프로젝트 경로 식별 하는 문자열입니다.  
  
 lpAuxProjPath  
 \[에서, out\] NULL 종결자를 포함 하 여 SCC\_PRJPATH\_SIZE\) \(최대 프로젝트를 식별 하는 보조 문자열입니다.  
  
 lpParentProjPath  
 \[에서, out\] NULL 종결자를 포함 하 여 SCC\_PRJPATH\_SIZE\) \(최대 부모 프로젝트 경로 식별 하는 출력 문자열입니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|부모 프로젝트 경로 가져왔습니다.|  
|SCC\_E\_INITIALIZEFAILED|프로젝트를 초기화할 수 없습니다.|  
|SCC\_E\_INVALIDUSER|사용자의 소스 제어 플러그 인에 로그인 하지 못했습니다.|  
|SCC\_E\_UNKNOWNPROJECT|프로젝트 소스 제어 플러그 인에 인식 되지 않습니다.|  
|SCC\_E\_INVALIDFILEPATH|잘못 되었거나 사용할 수 없는 파일 경로입니다.|  
|SCC\_E\_NOTAUTHORIZED|사용자가이 작업을 수행할 수 없습니다.|  
|SCC\_E\_ACCESSFAILURE|소스 제어 시스템에 경합 또는 네트워크 문제 때문에 액세스할 수 없습니다. 다시 시도 사용 하는 것이 좋습니다.|  
|SCC\_E\_PROJSYNTAXERR|잘못 된 프로젝트 구문입니다.|  
|SCC\_E\_CONNECTIONFAILURE|연결 문제를 저장 합니다.|  
|SCC\_E\_NONSPECIFICERROR<br /><br /> SCC\_E\_UNKNOWNERROR|알 수 없는 오류가 발생 했습니다.|  
  
## 설명  
 이 함수는 성공 또는 실패 코드를 반환 하 고, 성공 하는 경우 변수를 채웁니다 `lpParentProjPath` 지정된 된 프로젝트에 전체 프로젝트 경로 사용 합니다.  
  
 이 함수는 기존 프로젝트의 프로젝트 경로 부모를 반환합니다. 루트 프로젝트에 대 한 함수에 전달 된 프로젝트 경로 반환 \(즉, 동일한 루트 프로젝트 경로\). 프로젝트 경로 소스 제어 플러그 인에 의미 있는 문자열 않음을 유의 하십시오.  
  
 IDE의 변경 내용을 적용할 준비가 된 `lpUser` 및 `lpAuxProjPath` 도 매개 변수입니다. IDE는 이러한 문자열을 유지 하 고 전달 하는 [SccOpenProject](../extensibility/sccopenproject-function.md) 를 열 때이 프로젝트 나중에 있습니다. 따라서 이러한 문자열을 소스 제어 플러그 인을 프로젝트와 연결 하는 데 필요한 정보를 추적 하는 방법을 제공 합니다.  
  
 이 함수는는 [SccGetProjPath](../extensibility/sccgetprojpath-function.md), 점을 제외 하 고 프로젝트를 선택 하려면 사용자를 묻지 않습니다. 되지 기존 프로젝트에만 작동 하지만 새 프로젝트를 만듭니다.  
  
 때 `SccGetParentProjectPath` 이라고 `lpProjPath` 및 `lpAuxProjPath` 빈 되지 않으며 올바른 프로젝트에 해당 됩니다. 이러한 문자열에 대 한 이전 호출에서 IDE에서 받은 일반적으로 `SccGetProjPath` 함수입니다.  
  
 `lpUser` 인수는 사용자 이름입니다. IDE에서 이전에 수신한 것 같은 사용자 이름을 전달 합니다는 `SccGetProjPath` 함수 및 소스 제어 플러그 인 이름을 기본값으로 사용 해야 합니다. 사용자가 이미 열려 있는 연결 플러그 인을 하는 경우 다음 플러그 인 하려고 해야 함수는 자동으로 작동 하는지 확인 하는 프롬프트가 나타나지 않도록 합니다. 그러나 로그인이 실패 하면 플러그 인 메시지를 표시할 로그인 하 고, 한 유효한 로그인 이름에 다시 전달 받을 때 `lpUser`합니다. IDE는 크기의 버퍼를 할당할 항상 플러그 인이 문자열 바뀔 수, 있으므로 \(`SCC_USER_LEN`\+ 1\). 문자열 변경 되 면 새 문자열 \(적어도 기존 문자열 유효\) 유효한 로그인 이름 이어야 합니다.  
  
## SccCreateSubProject 및 SccGetParentProjectPath에 대 한 기술 참고 사항  
 소스 제어에 솔루션 및 프로젝트를 추가할 수 있는 사용자는 소스 제어 시스템에서 위치를 선택 하 라는 메시지가 표시 되는 횟수를 최소화 하기 위해 Visual Studio에서 간소화 되었습니다. 소스 제어 플러그 인을 지 원하는 새로운 함수는 모두 경우 이러한 변경 내용은 Visual Studio로 활성화 되는 [SccCreateSubProject](../extensibility/scccreatesubproject-function.md) 및 `SccGetParentProjectPath` 함수입니다. 그러나 이러한 변경 내용을 사용 하지 않도록 설정 하 여 이전 Visual Studio \(소스 제어 플러그 인 API 버전 1.1\) 동작으로 되돌리려면 다음 레지스트리 항목을 사용할 수 있습니다.  
  
 \[HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\8.0\\SourceControl\] "DoNotCreateSolutionRootFolderInSourceControl" \= dword: 00000001  
  
 이 레지스트리 항목이 존재 하지 않거나은로 설정 되어, 새 기능을 사용 하 여 Visual Studio 시도 `SccCreateSubProject`및`SccGetParentProjectPath`합니다.  
  
 레지스트리 항목 dword: 00000001로 설정 되 면 Visual Studio에서는 이러한 새 함수를 사용 하려고 하지 않습니다 및 소스 제어에 추가 하는 작업은 이전 버전의 Visual Studio에서와 마찬가지로 작동 합니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccCreateSubProject](../extensibility/scccreatesubproject-function.md)   
 [SccGetProjPath](../extensibility/sccgetprojpath-function.md)