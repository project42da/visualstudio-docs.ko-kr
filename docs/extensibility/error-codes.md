---
title: "오류 코드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "오류 코드, 소스 제어 플러그 인"
  - "소스 제어 플러그 인, 오류 코드"
  - "오류 [Visual Studio SDK]"
ms.assetid: d9cbd1c4-719b-467a-8100-333c1e146d3b
caps.latest.revision: 19
caps.handback.revision: 19
ms.author: "gregvanl"
manager: "ghogen"
---
# 오류 코드
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

소스 제어 플러그 인 API 함수에서 오류가 반환 하는 경우 다음 오류 코드 중 하나가 될 될 것입니다. 모든 오류를 경고 또는 정보 제공 용 이므로 오류 코드는 양수, 음수, 이며 성공 0입니다.  
  
|오류 코드|값|설명|  
|-----------|-------|--------|  
|`SCC_I_SHARESUBPROJOK`|7|플러그 인 지원 두 단계에서 소스 제어에서 파일을 추가 합니다. 자세한 내용은 [SccSetOption](../extensibility/sccsetoption-function.md)을 참조하세요.|  
|`SCC_I_FILEDIFFERS`|6|로컬 파일은 소스 제어 데이터베이스의 파일과 다릅니다 \(예를 들어 [SccDiff](../extensibility/sccdiff-function.md) 이 값을 반환할 수 있습니다\).|  
|`SCC_I_RELOADFILE`|5|소스 제어 작업; 하는 동안 로컬 파일 변경 IDE 해야 파일을 다시 로드 가능한 경우.|  
|`SCC_I_FILENOTAFFECTED`|4|파일의 영향을 받지 않습니다.|  
|`SCC_I_PROJECTCREATED`|3|소스 제어 작업 하는 동안 프로젝트를 만든 \(예를 들어 호출 하는 동안 [SccOpenProject](../extensibility/sccopenproject-function.md) 때 `SCC_OP_CREATEIFNEW` 플래그를 지정\).|  
|`SCC_I_OPERATIONCANCELED`|2|작업이 취소 되었습니다.|  
|`SCC_I_ADV_SUPPORT`|1|플러그 인 지정된 된 명령 위한 고급 옵션을 지원 합니다. 자세한 내용은 [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md)을 참조하세요.|  
|`SCC_OK`|0|명령 실행 성공|  
|`SCC_E_INITIALIZEFAILED`|\-1|오류: 초기화 하지 못했습니다.|  
|`SCC_E_UNKNOWNPROJECT`|\-2|오류: 프로젝트 알 수 없는 합니다.|  
|`SCC_E_COULDNOTCREATEPROJECT`|\-3|오류: 프로젝트를 만들 수 없습니다.|  
|`SCC_E_NOTCHECKEDOUT`|\-4|오류: 파일 체크 아웃 되지 않은 합니다.|  
|`SCC_E_ALREADYCHECKEDOUT`|\-5|오류: 파일은 이미 체크 아웃 합니다.|  
|`SCC_E_FILEISLOCKED`|\-6|오류: 파일이 잠겨 있습니다.|  
|`SCC_E_FILEOUTEXCLUSIVE`|\-7|오류: 파일 단독으로 체크 아웃 됩니다.|  
|`SCC_E_ACCESSFAILURE`|\-8|소스 제어 시스템에 경합 또는 네트워크 문제 때문에 액세스할 수 없습니다. 다시 시도 사용 하는 것이 좋습니다.|  
|`SCC_E_CHECKINCONFLICT`|\-9|오류: 체크 인하는 동안 충돌이 했습니다.|  
|`SCC_E_FILEALREADYEXISTS`|\-10|오류: 파일이 이미 있습니다.|  
|`SCC_E_FILENOTCONTROLLED`|\-11|오류: 파일이 아닙니다 소스 제어 합니다.|  
|`SCC_E_FILEISCHECKEDOUT`|\-12|오류: 파일 체크 아웃 됩니다.|  
|`SCC_E_NOSPECIFIEDVERSION`|\-13|오류: 버전이 없습니다 지정 합니다.|  
|`SCC_E_OPNOTSUPPORTED`|\-14|오류: 작업이 지원 되지 않습니다.|  
|`SCC_E_NONSPECIFICERROR`|\-15|알 수 없는 오류가 발생 했습니다.|  
|`SCC_E_OPNOTPERFORMED`|\-16|오류, 작업을 수행 하지 못했습니다.|  
|`SCC_E_TYPENOTSUPPORTED`|\-17|오류: 형식 예를 들어 파일의 이진, 소스 코드 제어 시스템에서 지원 되지 않습니다.|  
|`SCC_E_VERIFYMERGE`|\-18|파일 자동 병합 되었지만 보류 중인 사용자가 확인 있기 때문에 검사 하지 않은.|  
|`SCC_E_FIXMERGE`|\-19|파일 자동 병합 되었지만 병합 충돌 수동으로 해결 해야 하는 검사 하지 않았습니다.|  
|`SCC_E_SHELLFAILURE`|\-20|셸 실패로 인해 오류가 발생 했습니다.|  
|`SCC_E_INVALIDUSER`|\-21|오류: 사용자 올바르지 않습니다.|  
|`SCC_E_PROJECTALREADYOPEN`|\-22|오류: 프로젝트가 이미 열려 있습니다.|  
|`SCC_E_PROJSYNTAXERR`|\-23|프로젝트 구문 오류가 있습니다.|  
|`SCC_E_INVALIDFILEPATH`|\-24|오류: 파일 경로가 잘못 되었습니다.|  
|`SCC_E_PROJNOTOPEN`|\-25|오류: 프로젝트가 열려 있지 않습니다.|  
|`SCC_E_NOTAUTHORIZED`|\-26|오류: 사용자가이 작업을 수행할 수 있는 권한이 없습니다.|  
|`SCC_E_FILESYNTAXERR`|\-27|파일 구문 오류가 있습니다.|  
|`SCC_E_FILENOTEXIST`|\-28|오류, 로컬 파일 존재 하지 않습니다.|  
|`SCC_E_CONNECTIONFAILURE`|\-29|오류: 연결 오류가 발생이 했습니다.|  
|`SCC_E_UNKNOWNERROR`|\-30|알 수 없는 오류가 발생 했습니다.|  
|`SCC_E_BACKGROUNDGETINPROGRESS`|\-31|배경 get 작업이 현재 진행 중입니다.|  
  
## 빠른 검사를 제공 하는 매크로  
  
```cpp#  
IS_SCC_ERROR(rtn) (((rtn) < 0) ? TRUE : FALSE) IS_SCC_SUCCESS(rtn) (((rtn) == SCC_OK) ? TRUE : FALSE) IS_SCC_WARNING(rtn) (((rtn) > 0) ? TRUE : FALSE)  
```  
  
## 주의  
 모든 소스 제어 플러그 인 API 함수 \(제외 하 고는 [SccAdd](../extensibility/sccadd-function.md), [SccCheckin](../extensibility/scccheckin-function.md), 및 [SccDiff](../extensibility/sccdiff-function.md)\) 인수로 전달 되는 로컬 파일의 작업 폴더에 존재 하지 않는 경우 성공 하 합니다. IDE에 대 한 호출을 실행할 수 있습니다 예를 들어는 [SccCheckout](../extensibility/scccheckout-function.md) 또는 [SccUncheckout](../extensibility/sccuncheckout-function.md) 작업 폴더에 존재 하지 않는 했지만 소스 제어 시스템에 존재 하는 파일에 있습니다. 이 호출에 성공 합니다. 작업 폴더 또는 소스 제어 시스템에 파일이 없는 경우에 함수가 실패 합니다.  
  
 와 같은 특정 함수가 `SccAdd` 및 `SccCheckin`, 특히 반환 해야 `SCC_E_FILENOTEXIST` 작업 폴더의 파일은 존재 하지 않습니다. 다른 함수는 소스 제어 시스템에 유효한 파일 이름에는 함수는 작동 하는 경우 작업 파일은 존재 하지 않을 때를 성공으로 예상 됩니다.  
  
 소스 제어 플러그 인 플러그 인에 파일 읽기 전용 일부 작업 중 하는 경우에 작업 폴더에 파일에 대 한 권한이 대 한 어떠한가 정도 하지 확인 해야 합니다. 작업 폴더에 파일을 이동, 삭제 및\-컨트롤 외부에서 변경 될 수 있습니다.  
  
## 참고 항목  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)