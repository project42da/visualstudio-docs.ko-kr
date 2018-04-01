---
title: SccGetCommandOptions 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccGetCommandOptions
helpviewer_keywords:
- SccGetCommandOptions function
ms.assetid: bbe4aa4e-b4b0-403e-b7a0-5dd6eb24e5a9
caps.latest.revision: 14
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 3bce2922c961bf29f320f047a91057a638fe708a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="sccgetcommandoptions-function"></a>SccGetCommandOptions 함수
이 함수는 지정된 된 명령에 대 한 고급 옵션에 대 한 사용자를 묻습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccGetCommandOptions(  
   LPVOID pvContext,  
   HWND hWnd,  
   enum SCCCOMMAND iCommand,  
   LPCMDOPTS* ppvOptions  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pvContext  
 [in] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 hWnd  
 [in] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에를 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 iCommand  
 [in] 고급 옵션 요청 되는 명령 (참조 [명령 코드](../extensibility/command-code-enumerator.md) 가능한 값에 대 한).  
  
 ppvOptions  
 [in] 옵션 구조 (또한 수 `NULL`).  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|명령 실행 성공|  
|SCC_I_ADV_SUPPORT|소스 제어 플러그 인 명령에 대 한 고급 옵션을 지원합니다.|  
|SCC_I_OPERATIONCANCELED|사용자가 소스 제어 플러그 인에서의 취소 **옵션** 대화 상자.|  
|SCC_E_OPTNOTSUPPORTED|소스 제어 플러그 인이 작업을 지원 하지 않습니다.|  
|SCC_E_ISCHECKEDOUT|현재 체크 아웃 하는 파일에 대 한이 작업을 수행할 수 없습니다.|  
|SCC_E_ACCESSFAILURE|소스 제어 시스템에 네트워크 또는 경합 문제 때문에 액세스 하는 문제가 발생 했습니다. 다시 시도 하 여 것이 좋습니다.|  
|SCC_E_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다.|  
  
## <a name="remarks"></a>설명  
 처음으로이 함수를 호출 하는 IDE `ppvOptions` = `NULL` 소스 제어 플러그 인 지정된 된 명령에 대 한 고급 옵션 기능을 지원 하는지 확인 하 합니다. 사용자는 고급 옵션을 요청 하면 IDE이이 함수를 다시 호출 플러그 인는 해당 명령에 대 한 기능을 지원 않습니다, (일반적으로 구현 된 **고급** 대화 상자에서 단추) 에대한NULL이아닌포인터를제공합니다.`ppvOptions` 가리키는 `NULL` 포인터입니다. 플러그 인 private 구조체에서 사용자가 지정한 모든 고급 옵션을 저장 하 고 해당 구조에 대 한 포인터를 반환 `ppvOptions`합니다. 이 구조에 대 한 후속 호출을 포함 하 여,에 대해 알고 있어야 하는 기타 모든 소스 제어 플러그 인 API 함수에 전달 되는 `SccGetCommandOptions` 함수입니다.  
  
 예제는이 상황을 명확 하 게 하는 데 도움이 될 수 있습니다.  
  
 사용자가 선택 하는 **가져오기** 명령 및 IDE에서 표시는 **가져오기** 대화 상자. IDE 호출은 `SccGetCommandOptions` 작동 `iCommand` 로 설정 `SCC_COMMAND_GET` 및 `ppvOptions` 로 설정 `NULL`합니다. 이 값은 해석 된 질문으로 플러그 인 소스 제어로, "있습니까이 명령에 대 한 고급 옵션?" 플러그 인을 반환 하는 경우 `SCC_I_ADV_SUPPORT`, IDE 표시는 **고급** 단추 해당 **가져오기** 대화 상자.  
  
 처음으로 사용자가 클릭는 **고급** 단추, IDE 다시 호출 하는 `SccGetCommandOptions` 함수,이 이번에는 비-`NULL``ppvOptions` 가리키는 `NULL` 포인터입니다. 플러그 인 표시 됩니다는 자체 **옵션 가져오기** 대화 상자, 자체 구조에 해당 정보를 업데이트 하 고 해당 구조에 대 한 포인터를 반환 사용자에 게 정보를 묻는 `ppvOptions`합니다.  
  
 사용자가 클릭할 경우 **고급** 다시 동일한 대화 상자에서 IDE를 호출는 `SccGetCommandOptions` 함수를 변경 하지 않고 다시 `ppvOptions`구조는 플러그 인으로 다시 전달 되도록 합니다. 이 통해 사용자가 이전에 설정 된 값으로 해당 대화 상자를 다시 초기화 하도록 플러그 인 합니다. 플러그 인을 반환 하기 전에 준비에서 구조를 수정합니다.  
  
 사용자가 클릭할 때을 마지막으로, **확인** IDE의에서 **가져오기** 대화 상자, IDE 호출은 [SccGet](../extensibility/sccget-function.md)에 반환 된 구조체에 전달 `ppvOptions` 를 포함 하는 고급 옵션입니다.  
  
> [!NOTE]
>  명령 `SCC_COMMAND_OPTIONS` IDE 표시 될 때 사용 되는 **옵션** 사용자 수 있는 대화 상자에는 통합 작동 방식을 제어 하는 환경을 설정 합니다. 표시 하려면 소스 제어 플러그 인를 자체 기본 설정 대화 상자를 제공 하려는 경우는 **고급** IDE의 기본 설정 대화 상자에서 단추입니다. 플러그 인은 전적으로 부담을 가져오고이 정보를 유지 합니다. IDE 사용 하거나 수정 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [명령 코드](../extensibility/command-code-enumerator.md)