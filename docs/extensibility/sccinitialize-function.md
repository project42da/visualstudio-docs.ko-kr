---
title: "SccInitialize 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccInitialize
helpviewer_keywords: SccInitialize function
ms.assetid: 5bc0d28b-2c68-4d43-9e51-541506a8f76e
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 6bf217218dcc1830cc2acf2833aa7e31e85745d9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="sccinitialize-function"></a>SccInitialize 함수
이 함수 소스 제어 플러그 인을 초기화 하 고 기능 및 통합된 개발 환경 (IDE)에 대 한 제한을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccInitialize (  
   LPVOID* ppvContext,  
   HWND    hWnd,  
   LPCSTR  lpCallerName,  
   LPSTR   lpSccName,  
   LPLONG  lpSccCaps,  
   LPSTR   lpAuxPathLabel,  
   LPLONG  pnCheckoutCommentLen,  
   LPLONG  pnCommentLen  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppvContext`  
 [in] 소스 제어 플러그 인 여기 해당 상황에 맞는 구조에 대 한 포인터를 배치할 수 있습니다.  
  
 `hWnd`  
 [in] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에를 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 `lpCallerName`  
 [in] 소스 제어 플러그 인을 호출 하는 프로그램의 이름입니다.  
  
 `lpSccName`  
 [out에서] 여기서 소스 제어 플러그 인 전환 자체 이름 버퍼 (넘지 `SCC_NAME_LEN`).  
  
 `lpSccCaps`  
 [out] 소스 제어 기능 플래그 인를 반환합니다.  
  
 `lpAuxPathLabel`  
 [out에서] 소스 제어 플러그 인에 대해 설명 하는 문자열을 배치 하는 위치 버퍼는 `lpAuxProjPath` 매개 변수에서 반환 되는 [SccOpenProject](../extensibility/sccopenproject-function.md) 및 [SccGetProjPath](../extensibility/sccgetprojpath-function.md) (넘지 `SCC_AUXLABEL_LEN`).  
  
 `pnCheckoutCommentLen`  
 [out] 체크 아웃 설명에 대 한 최대 허용 길이 반환합니다.  
  
 `pnCommentLen`  
 [out] 다른 주석에 대 한 최대 허용 길이 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|소스 제어 초기화에 성공 했습니다.|  
|SCC_E_INITIALIZEFAILED|시스템을 초기화할 수 없습니다.|  
|SCC_E_NOTAUTHORIZED|사용자 지정된 작업을 수행할 수 없습니다.|  
|SCC_E_NONSPECFICERROR|알 수 없는 오류입니다. 소스 제어 시스템을 초기화 하지 못했습니다.|  
  
## <a name="remarks"></a>설명  
 소스 제어 플러그 인을 처음 로드 될 때 IDE에서이 함수를 호출 합니다. IDE에서를이 플러그 인에 호출자에 게 이름 등의 특정 정보를 전달할 수 있습니다. IDE 가져옵니다 다시 주석 및 기능에 대 한 플러그 인에 대 한 허용 되는 최대 길이 등의 특정 정보가 있습니다.  
  
 `ppvContext` 가리키는 `NULL` 포인터입니다. 소스 제어 플러그 인 수 자체 용도에 구조를 할당 하 고 해당 구조에 대 한 포인터를 저장 `ppvContext`합니다. IDE는 플러그 인 전역 저장소에 문의 하지 않고 컨텍스트 정보가 필요 하 고 플러그 인의 여러 인스턴스를 지원 하도록 허용이 포인터 마다 다른 VSSCI API 함수에 전달 됩니다. 이 구조를 할당 취소할 때는 [SccUninitialize](../extensibility/sccuninitialize-function.md) 호출 됩니다.  
  
 `lpCallerName` 및 `lpSccName` 매개 변수 이름은 교환 하는 소스 제어 플러그 인 및 IDE를 사용 합니다. 실제로 메뉴 또는 대화 상자에 표시 될 수 또는 여러 인스턴스를 구별할 수에 단순히 이러한 이름은 사용할 수 있습니다.  
  
 `lpAuxPathLabel` 매개 변수는 솔루션 파일에 저장 되 고 소스 제어 플러그 인에 대 한 호출에 전달 하는 보조 프로젝트 경로 확인 하는 주석으로 사용 되는 문자열은 [SccOpenProject](../extensibility/sccopenproject-function.md)합니다. [!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)]문자열을 사용 하 여 "SourceSafe 프로젝트:"; 이 특정 문자열을 사용 하 여 다른 소스 제어 플러그 인이 포함 되지 않습니다 해야 합니다.  
  
 `lpSccCaps` 매개 변수는 소스 제어를 제공 플러그 인에 대 한 플러그 인 기능을 나타내는 비트를 저장 합니다. (기능 비트 전체 목록을 참조 하십시오. [기능 플래그](../extensibility/capability-flags.md)). 예를 들어, 기능을 설정 하는 플러그 인을 호출자에 게 제공 콜백 함수로 결과 기록 하도록 하는 플러그 인 계획 SCC_CAP_TEXTOUT 비트 경우. 버전 제어 결과 대 한 창을 만들지 IDE를 신호로 알리는 것이 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccUninitialize](../extensibility/sccuninitialize-function.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)   
 [기능 플래그](../extensibility/capability-flags.md)