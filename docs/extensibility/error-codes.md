---
title: "오류 코드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- error codes, source control plug-ins
- source control plug-ins, error codes
- errors [Visual Studio SDK]
ms.assetid: d9cbd1c4-719b-467a-8100-333c1e146d3b
caps.latest.revision: "19"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 50d05e529a3202f59df53801728b40fee1c68f40
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="error-codes"></a>오류 코드
소스 제어 플러그 인 API 함수에서 오류를 반환 하는 경우 다음 오류 코드 중 하나를 사용할 수 있습니다. 모든 오류를 경고 또는 정보 제공 용 이므로 오류 코드는 양수, 음수 이면 고, 성공이 0입니다.  
  
|오류 코드|값|설명|  
|----------------|-----------|-----------------|  
|`SCC_I_SHARESUBPROJOK`|7|플러그 인을 지원 두 단계에서 소스 제어에서 파일을 추가 합니다. 자세한 내용은 참조 [SccSetOption](../extensibility/sccsetoption-function.md)합니다.|  
|`SCC_I_FILEDIFFERS`|6|로컬 파일은 소스 제어 데이터베이스에서 파일 다릅니다 (예를 들어 [SccDiff](../extensibility/sccdiff-function.md) 이 값을 반환할 수 있습니다).|  
|`SCC_I_RELOADFILE`|5|소스 제어 작업; 하는 동안 로컬 파일 변경 IDE 해야 파일 다시 로드 가능한 경우.|  
|`SCC_I_FILENOTAFFECTED`|4|파일의 영향을 받지 않습니다.|  
|`SCC_I_PROJECTCREATED`|3|프로젝트를 소스 제어 작업 하는 동안 만든 (예를 들어 호출 하는 동안 [SccOpenProject](../extensibility/sccopenproject-function.md) 때 `SCC_OP_CREATEIFNEW` 플래그가 지정 된).|  
|`SCC_I_OPERATIONCANCELED`|2|작업이 취소 되었습니다.|  
|`SCC_I_ADV_SUPPORT`|1|플러그 인 지정된 된 명령의 위한 고급 옵션을 지원 합니다. 자세한 내용은 참조 [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md)합니다.|  
|`SCC_OK`|0|명령 실행 성공|  
|`SCC_E_INITIALIZEFAILED`|-1|오류: 초기화 하지 못했습니다.|  
|`SCC_E_UNKNOWNPROJECT`|-2|오류: 프로젝트는 알려진 아닙니다.|  
|`SCC_E_COULDNOTCREATEPROJECT`|-3|오류: 프로젝트를 만들 수 없습니다.|  
|`SCC_E_NOTCHECKEDOUT`|-4|오류: 파일 확인 하지 않습니다.|  
|`SCC_E_ALREADYCHECKEDOUT`|-5|오류: 파일은 이미 체크 아웃 합니다.|  
|`SCC_E_FILEISLOCKED`|-6|오류: 파일이 잠겨 있습니다.|  
|`SCC_E_FILEOUTEXCLUSIVE`|-7|오류: 파일 단독으로 체크 아웃 됩니다.|  
|`SCC_E_ACCESSFAILURE`|-8|소스 제어 시스템에 네트워크 또는 경합 문제 때문에 액세스 하는 문제가 발생 했습니다. 다시 시도 하 여 것이 좋습니다.|  
|`SCC_E_CHECKINCONFLICT`|-9|오류: 체크 인하는 동안 충돌이 발생 했습니다.|  
|`SCC_E_FILEALREADYEXISTS`|-10|오류: 파일이 이미 있습니다.|  
|`SCC_E_FILENOTCONTROLLED`|-11|오류: 파일 소스 제어 하지 되었습니다.|  
|`SCC_E_FILEISCHECKEDOUT`|-12|오류: 파일 체크 아웃 됩니다.|  
|`SCC_E_NOSPECIFIEDVERSION`|-13|오류: 된 지정 된 버전이 없습니다.|  
|`SCC_E_OPNOTSUPPORTED`|-14|오류: 작업이 지원 되지 않습니다.|  
|`SCC_E_NONSPECIFICERROR`|-15|알 수 없는 오류가 발생 했습니다.|  
|`SCC_E_OPNOTPERFORMED`|-16|오류, 작업을 수행 하지 못했습니다.|  
|`SCC_E_TYPENOTSUPPORTED`|-17|오류: 형식 예를 들어 파일의 이진, 소스 코드 제어 시스템에서 지원 되지 않습니다.|  
|`SCC_E_VERIFYMERGE`|-18|파일 자동 병합 되었지만 보류 중인 사용자가 확인 되었기 때문에 확인 되지 않습니다.|  
|`SCC_E_FIXMERGE`|-19|파일 자동 병합 되었지만 인해 병합 충돌이 수동으로 해결 해야 하는 검사 하지 않았습니다.|  
|`SCC_E_SHELLFAILURE`|-20|셸 실패로 인해 오류가 발생 했습니다.|  
|`SCC_E_INVALIDUSER`|-21|오류: 사용자가 잘못 되었습니다.|  
|`SCC_E_PROJECTALREADYOPEN`|-22|오류: 프로젝트가 이미 열려 있습니다.|  
|`SCC_E_PROJSYNTAXERR`|-23|프로젝트 구문 오류가 있습니다.|  
|`SCC_E_INVALIDFILEPATH`|-24|오류: 파일 경로가 잘못 되었습니다.|  
|`SCC_E_PROJNOTOPEN`|-25|오류: 프로젝트가 열려 있지 않습니다.|  
|`SCC_E_NOTAUTHORIZED`|-26|오류: 사용자는이 작업을 수행할 권한이 없습니다.|  
|`SCC_E_FILESYNTAXERR`|-27|파일 구문 오류가 있습니다.|  
|`SCC_E_FILENOTEXIST`|-28|오류를 로컬 파일 존재 하지 않습니다.|  
|`SCC_E_CONNECTIONFAILURE`|-29|오류: 연결 실패가 했습니다.|  
|`SCC_E_UNKNOWNERROR`|-30|알 수 없는 오류가 발생 했습니다.|  
|`SCC_E_BACKGROUNDGETINPROGRESS`|-31|배경 get 작업이 현재 진행 중입니다.|  
  
## <a name="macros-provided-for-quick-checking"></a>빠른 검사에 대 한 제공 매크로  
  
```cpp  
IS_SCC_ERROR(rtn) (((rtn) < 0) ? TRUE : FALSE)  
IS_SCC_SUCCESS(rtn) (((rtn) == SCC_OK) ? TRUE : FALSE)  
IS_SCC_WARNING(rtn) (((rtn) > 0) ? TRUE : FALSE)  
```  
  
## <a name="remarks"></a>설명  
 모든 소스 제어 플러그 인 API 함수 (제외 하 고는 [SccAdd](../extensibility/sccadd-function.md), [SccCheckin](../extensibility/scccheckin-function.md), 및 [SccDiff](../extensibility/sccdiff-function.md)) 인수로 전달 되는 로컬 파일에서 수행 하는 경우 성공 하 작업 폴더에 없습니다. 예를 들어 IDE에 대 한 호출 발행는 [SccCheckout](../extensibility/scccheckout-function.md) 또는 [SccUncheckout](../extensibility/sccuncheckout-function.md) 작업 폴더에 존재 하지 않는 했지만 소스 제어 시스템에 존재 하는 파일에 있습니다. 이 호출에 성공 합니다. 작업 폴더에 또는 소스 제어 시스템에 파일이 없는 경우에 함수가 실패 합니다.  
  
 와 같은 특정 함수가 `SccAdd` 및 `SccCheckin`, 특히 반환 해야 `SCC_E_FILENOTEXIST` 작업 폴더의 파일은 존재 하지 않습니다. 다른 함수는 소스 제어 시스템에 유효한 파일 이름에는 함수를 실행 하는 경우 작업 파일은 존재 하지 않을 때 성공으로 예상 됩니다.  
  
 소스 제어 플러그 인 플러그 인에 파일 읽기 전용으로 표시 일부 작업 중 경우에 작업 폴더에서 파일에 대 한 권한이 관한 어떠한가 정도 하지 확인 해야 합니다. 작업 폴더의 파일에에서는 이동, 삭제 및-컨트롤 외부에서 변경 될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)