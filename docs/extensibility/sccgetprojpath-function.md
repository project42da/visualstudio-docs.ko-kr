---
title: "SccGetProjPath 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccGetProjPath"
helpviewer_keywords: 
  - "SccGetProjPath 함수"
ms.assetid: 1079847e-d45f-4cb8-9d92-1e01ce5d08f6
caps.latest.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 15
---
# SccGetProjPath 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 프로젝트 경로 소스 제어 플러그 인에 의미 하는 문자열에 대 한 사용자를 묻습니다. 사용자가 때 호출 됩니다.  
  
-   새 프로젝트 만들기  
  
-   버전 제어에 기존 프로젝트 추가  
  
-   기존 버전 제어 프로젝트를 찾으려고 시도 합니다.  
  
## 구문  
  
```cpp#  
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
  
#### 매개 변수  
 pvContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 hWnd  
 \[in\] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에 대 한 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 lpUser  
 \[에서, out\] 사용자 이름 \(NULL 종결자를 포함 하 여 SCC\_USER\_SIZE를 초과 하지 않음\)  
  
 lpProjName  
 \[에서, out\] IDE 프로젝트, 프로젝트 작업 영역 또는 메이크파일 \(NULL 종결자를 포함 하 여 SCC\_PRJPATH\_SIZE를 초과 하지 않음\)의 이름입니다.  
  
 lpLocalPath  
 \[에서, out\] 프로젝트의 작업 경로입니다. 경우 `bAllowChangePath` 은 `TRUE`, 소스 제어 플러그 인이 문자열 \(null 종결자를 포함 하 여 \_MAX\_PATH를 초과 하지 않음\)를 수정할 수 있습니다.  
  
 lpAuxProjPath  
 \[에서, out\] 반환 된 프로젝트 경로 \(NULL 종결자를 포함 하 여 SCC\_PRJPATH\_SIZE를 초과 하지 않음\)에 대 한 버퍼입니다.  
  
 bAllowChangePath  
 \[in\] 이것이 `TRUE`, 소스 제어 플러그 인에 대 한 메시지를 표시 하 고 수정할 수는 `lpLocalPath` 문자열입니다.  
  
 pbNew  
 \[에서, out\] 값의 새 프로젝트를 만들려면 여부를 나타냅니다. 반환 된 값에는 프로젝트를 만드는 방법을 성공을 나타냅니다.  
  
|들어오|해석|  
|---------|--------|  
|TRUE|사용자는 새 프로젝트를 만들 수 있습니다.|  
|FALSE|사용자는 새 프로젝트를 만들 수 없습니다.|  
  
|나가는 포트|해석|  
|------------|--------|  
|TRUE|새 프로젝트를 만들었습니다.|  
|FALSE|기존 프로젝트를 선택 했습니다.|  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|성공적으로 프로젝트를 만들거나 검색 됩니다.|  
|SCC\_I\_OPERATIONCANCELED|작업이 취소 되었습니다.|  
|SCC\_E\_ACCESSFAILURE|소스 제어 시스템에 경합 또는 네트워크 문제 때문에 액세스할 수 없습니다.|  
|SCC\_E\_CONNECTIONFAILURE|소스 제어 시스템에 연결 하는 동안 문제가 발생 했습니다.|  
|SCC\_E\_NONSPECIFICERROR|오류가 발생 했습니다.|  
  
## 설명  
 이 함수는 매개 변수를 얻으려고 ide `lpProjName` 및 `lpAuxProjPath`합니다. 이 정보를 묻는 메시지를 표시 하는 소스 제어 플러그 인, 후 이러한 두 문자열 IDE에 다시 전달 합니다. IDE의 솔루션 파일에 이러한 문자열을 지속 하 고 파이프라인 연산자는 [SccOpenProject](../extensibility/sccopenproject-function.md) 사용자가이 프로젝트를 열 때마다 합니다. 이러한 문자열을 프로젝트와 관련 된 정보를 추적 플러그 인을 사용 합니다.  
  
 함수에 처음으로 호출 하는 경우 `lpAuxProjPath` 을 빈 문자열로 설정 됩니다.`lProjName` 또한 비어 있을 수 소스 제어 플러그 인 사용 하거나 무시할 수 있는 IDE 프로젝트 이름을 포함할 수 있습니다. 함수가 성공적으로 반환 될 때 해당 문자열 두 플러그 인 반환 합니다. IDE 이러한 문자열에 대 한 가정을 하지 않고 하 고 사용 되지 않을 것을 수정 하는 사용자를 허용 하지 않습니다. 사용자가 설정을 변경 하려는 경우 IDE에서 호출 `SccGetProjPath` 다시 동일한 값의 전달 받았다면 이전 시간입니다. 이러한 두 문자열을 완전히 제어할은 플러그 인을 제공 합니다.  
  
 에 대 한 `lpUser`, IDE는 사용자 이름에 전달할 수 있습니다, 또는 단순히 빈 문자열에 대 한 포인터에 통과할 수 있습니다. 사용자 이름이 없으면 소스 제어 플러그 인을 기본값으로 사용 해야 합니다. 그러나 이름이 전달 되지 않은 경우 또는 지정 된 이름의 로그인에 실패 한 경우 플러그 인에서 메시지를 표시 한 로그인 및 이름에 다시 전달에 대 한 사용자 `lpUser` 유효한 로그인을 받을 때입니다. IDE는 크기의 버퍼를 할당할 항상 플러그 인이 문자열 바뀔 수, 있으므로 \(`SCC_USER_LEN`\+ 1\).  
  
> [!NOTE]
>  IDE를 수행 하는 첫 번째 작업 중 하나에 대 한 호출 수는 `SccOpenProject` 함수 또는 `SccGetProjPath` 함수입니다. 따라서 그 중 둘 다 동일한 `lpUser` 매개 변수를 소스 제어 플러그 타임에 사용자를 로그인 할 수 있게 해줍니다. 함수에서 반환 된 값 오류가 발생 했음을 나타냅니다, 경우에 플러그 인 채워야 유효한 로그인 이름으로이 문자열입니다.  
  
 `lpLocalPath` 디렉터리는 사용자가 프로젝트를 보관 하는 곳입니다. 빈 문자열일 수 있습니다. 디렉터리가 없습니다 \(의 경우 처럼 소스 제어 시스템에서 프로젝트를 다운로드 하는 사용자\) 현재 정의 되어 있는 경우 `bAllowChangePath` 은 `TRUE`, 소스 제어 플러그 인 사용자 입력에 대 한 메시지를 표시 하거나 다른 방법에는 자체 문자열을 사용 하 여 수 `lpLocalPath`합니다. 경우 `bAllowChangePath` 은 `FALSE`, 플러그 인 변경해 서는 안 문자열, 사용자가 이미 지정된 된 디렉터리에서 작업 하기 때문에 있습니다.  
  
 사용자 소스 제어에서 적용할 새 프로젝트를 만드는 경우 소스 제어 플러그 인 만들지 못할 수도 있습니다 실제로 그 소스 제어 시스템에서 시간에 `SccGetProjPath` 호출 됩니다. 그 대신, 전달 다시 0이 아닌 값을 사용 하 여 함께 문자열 `pbNew`, 프로젝트 소스 제어 시스템에서 만들어졌는지 나타내는 합니다.  
  
 예를 들어 사용자는 **새 프로젝트** Visual Studio에서 마법사가 자신의 프로젝트가 소스 제어에 추가 하 고이 함수를 호출 하는 Visual Studio 플러그 인 오류가 있는지를 Visual Studio 프로젝트를 포함 하 여 소스 제어 시스템에서 새 프로젝트를 만들 수 있습니다. 사용자가 클릭할 경우 **취소** 마법사를 완료 하기 전에 프로젝트 만들어지지 않습니다. 사용자가 클릭할 경우 **확인**, Visual Studio에서 호출 `SccOpenProject`, 전달, `SCC_OPT_CREATEIFNEW`, 소스 제어 프로젝트는 해당 시점에 생성 됩니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)